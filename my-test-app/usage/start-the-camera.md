---
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Start the camera

To start using the SDK we need to [start the camera ](start-the-camera.md), for this reason we need a lifecycle like an activity or a fragment and implement these lines of code in the Activity: first we start the camera, second preview is attached.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
class MainActivity : ComponentActivity() {
   }
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        Gizo.app.gizoAnalysis.startCamera(lifecycleOwner = this) {

        }
        setContent {
            val context = LocalContext.current
            val isPermissionGranted = remember { mutableStateOf(false) }

            val launcherDrivePermission = rememberLauncherForActivityResult(
                ActivityResultContracts.RequestMultiplePermissions()
            ) { permissionsMap ->
                val areGranted = permissionsMap.mapNotNull {
                    it.value
                }.reduce { acc, next -> acc && next }

                if (areGranted){
                    isPermissionGranted.value = true
                }
            }

            LaunchedEffect(true){
                checkAndRequestLocationPermissions(
                    context,
                    recordingPermission,
                    launcherDrivePermission
                ) {
                    isPermissionGranted.value = true
                }
            }

            if(isPermissionGranted.value){
                Screen(context)
            }
        }
    }
}

@Composable
fun Screen(context : Context) {
    val previewView: PreviewView = remember { PreviewView(context) }

    LaunchedEffect(previewView) {
        previewView.implementationMode = PreviewView.ImplementationMode.COMPATIBLE
        Gizo.app.gizoAnalysis.attachPreview(previewView)
    }

    previewView.let { preview ->
        AndroidView(
            factory = { preview },
            modifier = Modifier.fillMaxSize()
        )
    }
}

```
{% endtab %}
{% endtabs %}

To remove the toolbar from screen, create this style in Theme, then add the style to the Manifest.

{% tabs %}
{% tab title="Themes.xml" %}
```kotlin
<style name="Theme.Gizo.Recording" parent="Theme.AppCompat.Light.NoActionBar">
    <item name="windowActionBarOverlay">false</item>
    <item name="android:windowFullscreen">true</item>
</style>
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="AndroidManigest.xml" %}
<pre class="language-kotlin"><code class="lang-kotlin">&#x3C;activity
<strong>    android:screenOrientation="landscape"
</strong>    android:theme="@style/Theme.Gizo.Recording">
&#x3C;/activity>
</code></pre>
{% endtab %}
{% endtabs %}
