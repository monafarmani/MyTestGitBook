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

# ⚙ Usage

## Using the SDK in your Android Application

### <mark style="color:purple;">Step 1: Initialize the SDK</mark>

To initialize the SDK, you will need to create a new instance of the Application class in your app's module:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
class Application : Application() {

    override fun onCreate() {
        super.onCreate()

        Gizo.initialize(
            this,
            GizoApp.GizoAppOptions.Builder().build()
        )
    }
}
```
{% endtab %}
{% endtabs %}

In the example above, we create a new instance of the Application class and call the initialize method to initialize the sdk.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
<application
    android:name=".Application"
>
```
{% endtab %}
{% endtabs %}

In the examole above, we add some lines of code to AndroidManifest.xml as well.



**Note:** For using features of the sdk you need to add [Model ](app-options-setting/gizoanalysissettings.md)and  required [App Options Setting](app-options-setting/) in the following steps.



### <mark style="color:purple;">Step 2: Permissions settings</mark>

The following permissions are required by the SDK:

<table><thead><tr><th width="348">PERMISSIONS</th><th>WHERE TO USE</th></tr></thead><tbody><tr><td>ACCESS_COARSE_LOCATION</td><td>in gps setting.</td></tr><tr><td>ACCESS_FINE_LOCATION</td><td>in gps setting.</td></tr><tr><td>CAMERA</td><td>in capturing videos.</td></tr><tr><td>ACCESS_NETWORK_STATE</td><td>in mapbox navigation.</td></tr><tr><td>WRITE_EXTERNAL_STORAGE</td><td>in saving files in download folder.</td></tr></tbody></table>

### Permissions Required

The following permissions are required by the SDK:

#### <mark style="color:blue;">ACCESS\_COARSE\_LOCATION</mark>

The ACCESS\_COARSE\_LOCATION permission is required to obtain the user's approximate location. This permission is used to provide location-based services to the user, such as displaying relevant content based on their location.

**Note**: This permission does not grant access to the user's precise location or any other location-related features, such as the ability to track the user's movements.

To request the ACCESS\_COARSE\_LOCATION permission in your app, add the following line to your app's Manifest file:

{% tabs %}
{% tab title="xml" %}
```kotlin
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
```
{% endtab %}
{% endtabs %}

#### <mark style="color:blue;">ACCESS\_FINE\_LOCATION</mark>&#x20;

The ACCESS\_FINE\_LOCATION permission is required to obtain the user's precise location. This permission is used to provide location-based services to the user, such as displaying nearby points of interest or providing turn-by-turn directions.

**Note**: This permission grants access to the user's precise location data, which can be used to track the user's movements. Make sure to handle the user's location data responsibly and in accordance with your app's privacy policy.

To request the ACCESS\_FINE\_LOCATION permission in your app, add the following line to your app's Manifest file:

{% tabs %}
{% tab title="xml" %}
```kotlin
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
```
{% endtab %}
{% endtabs %}

#### <mark style="color:blue;">CAMERA</mark>

&#x20;The CAMERA permission is required to capture images and scan QR codes. Without this permission, the SDK will not be able to perform these functions.

**Note**: This permission does not grant access to other camera-related features, such as the microphone or location data.

To request the CAMERA permission in your app, add the following line to your app's Manifest file:



{% tabs %}
{% tab title="xml" %}
```kotlin
<uses-permission android:name="android.permission.CAMERA" />
```
{% endtab %}
{% endtabs %}

#### <mark style="color:blue;">ACCESS\_NETWORK\_STATE</mark>

The ACCESS\_NETWORK\_STATE permission is required to determine the user's network connectivity status. This permission is used to check if the user is connected to the internet or not, and to adjust the SDK's behavior accordingly.

To request the ACCESS\_NETWORK\_STATE permission in your app, add the following line to your app's Manifest file:

{% tabs %}
{% tab title="xml" %}
```kotlin
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```
{% endtab %}
{% endtabs %}

#### <mark style="color:blue;">WRITE\_EXTERNAL\_STORAGE</mark>

&#x20;The WRITE\_EXTERNAL\_STORAGE permission is required to write files to the user's external storage, such as saving photos or documents. This permission is used to enable features of the SDK that require the ability to save files, such as file download or export functionality.

**Note**: This permission does not grant access to other external storage-related features, such as the ability to delete files.

To request the WRITE\_EXTERNAL\_STORAGE permission in your app, add the following line to your app's Manifest file:

{% tabs %}
{% tab title="xml" %}
```kotlin
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```
{% endtab %}
{% endtabs %}

































## Interacting with the rationale dialog

Implement the `EasyPermissions.RationaleCallbacks` if you want to interact with the rationale dialog.@Override

```
public void onRationaleAccepted(int requestCode) {
    // Rationale accepted to request some permissions
    // ...
}

@Override
public void onRationaleDenied(int requestCode) {
    // Rationale denied to request some permissions
    // ...
}
```

Rationale callbacks don't necessarily imply permission changes. To check for those, see the `EasyPermissions.PermissionCallbacks`.



## Available attributes for Element Class



<table data-full-width="false"><thead><tr><th>Function</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>setTitle(String)</td><td>Set title of the element</td><td></td></tr><tr><td>setIconTint(Int)</td><td>Set color of the element</td><td></td></tr><tr><td>setSkipTint(Boolean)</td><td>Skip tinting the icon (useful when using non vector drawables)</td><td></td></tr><tr><td>setValue(String)</td><td>Set icon of the element</td><td></td></tr><tr><td>setIntent(Intent)</td><td>Set Element value like Facebook ID</td><td></td></tr></tbody></table>



## How to use the library in a fragment





## Styling

The library supports day-night modes. The dependents may use the following styling attributes to create a dedicated style for `AboutPage`. If the dependents choose not to specify an explicit style, the library falls back to sensible defaults.

First, declare an `AboutPage` style in your `styles.xml`.

```
<!-- Define a global style for AboutPage in your 'styles.xml' -->
<style name="Widget.App.AboutPage" parent="about_About">
  <item name="aboutBackground">#ffffff</item>
  <item name="aboutElementIconTint">#333333</item>
  <item name="aboutSeparatorColor">#999999</item>
  <item name="aboutDescriptionTextAppearance">@style/TextAppearance.App.AboutPage.Description</item>

  <!-- similarly, you can also apply the following text appearances -->
  <item name="aboutElementTextAppearance">@style/about_elementTextAppearance.Dark</item>
  <item name="aboutGroupTextAppearance">@style/about_groupTextAppearance</item>
</style>

<style name="TextAppearance.App.AboutPage.Description" parent="about_descriptionTextAppearance.Dark">
  <item name="android:textStyle">bold|italic</item>
</style>
```

To apply this style globally, assign its reference to `aboutStyle` attribute in your app theme.

```
<style name="Theme.App" parent="Theme.AppCompat">
  <item name="aboutStyle">@style/Widget.AboutPage</item>
</style>
```

Or explicitly pass the style resource to the `AboutPage` constructor to apply it on selective `AboutPage` instances.

```
AboutPage aboutPage = new AboutPage(context, R.style.Widget_AboutPage);

```

## &#x20;Force Night/Day mode

We recommend that the dependents use [`AppCompatDelegate.setDefaultNightMode()`](https://developer.android.com/reference/androidx/appcompat/app/AppCompatDelegate#setDefaultNightMode\(int\)) to force enable/disable the night mode across their apps. If the dependents are unable to use the recommended approach, they can use the `AboutPage(Context, boolean)` constructor to specify the desired mode. The dependents must note that by using this constructor, the `AboutPage` will use its default styles, ignoring any explicitly specified style.

```
AboutPage aboutPage = AboutPage(context, true); // force enable dark mode.
AboutPage aboutPage = AboutPage(context, false); // force enable bright mode.

```

## Sample Project