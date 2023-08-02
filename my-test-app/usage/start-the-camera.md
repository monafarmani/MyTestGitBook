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

To start to use the sdk we need to [start the camera ](start-the-camera.md), for this reason we need a lifecycle like an activity or a fragment and implement these lines of code in the  Activity: first we start the camera, second preview is attached.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
class MainActivity : ComponentActivity() {

    val preview: Preview? = null
    
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        Gizo.app.gizoAnalysis.startCamera(lifecycleOwner = lifecycleOwner) {

        }
        setContent {
            val context = LocalContext.current
            val previewView: PreviewView = remember { PreviewView(context) }

            LaunchedEffect(previewView) {
                previewView.implementationMode = PreviewView.ImplementationMode.COMPATIBLE
                Gizo.app.gizoAnalysis.attachPreview(previewView)
            }


            TestSdkTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    previewView.let { preview ->
                        AndroidView(
                            factory = { preview },
                            modifier = Modifier.fillMaxSize()
                        )
                    }
                    Greeting("Android")
                }
            }
        }
    }

```
{% endtab %}
{% endtabs %}
