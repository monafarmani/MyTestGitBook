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

# Gizo Analysis

## Overview

In this library, using artificial intelligence, the driving behavior is analyzed, and a series of data is computed to reduce the risk of accidents and other driving problems. As a result, the possibility of smarter and safer driving is provided for users.

###

### <mark style="color:purple;">Start Gizo Analysis</mark>

To start using the SDK we need to start Gizo Analysis. for this reason we need a lifecycle like an activity or a fragment and implement these lines of code in the Activity.

In Android development, a lifecycle refers to the series of states that an Android component, such as an Activity or Fragment, goes through during its existence. The Android framework provides a set of predefined methods that allow developers to perform specific actions or respond to events at different stages of the component's lifecycle.

The typical lifecycle of an Android component includes the following states: Created, Started, Resumed, Paused, Stopped & Destroyed.

Based on the [settings](app-options-setting/) applied by the developer, a series of features will be added to the SDK.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 Gizo.app.gizoAnalysis.start(lifecycleOwner = this, onDone = {})
```
{% endtab %}
{% endtabs %}

**onDone is called when start Gizo Analysis is completed.**

###

### <mark style="color:purple;">Stop Gizo Analysis</mark>

Whenever we no longer need the SDK, we should call the stop function to halt all ongoing operations within the library. These processes include video recording, GPS, IMU, Analysis and so on..&#x20;

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
  Gizo.app.gizoAnalysis.stop()
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Start saving session</mark>

Based on the settings we have applied, some files related to video , Analysis , gps and Imu are saved.

Saving files like GPS data, videos, IMU data, and analysis results in Android Studio provides benefits such as data persistence, offline accessibility, advanced data analysis, sharing and collaboration, data backup and recovery, and historical tracking. It enhances the functionality, usability, and reliability of your app by ensuring the availability and integrity of important data

To start saving files using MyTestSDK , use the following code:

{% tabs %}
{% tab title="Kotlin" %}
<pre class="language-kotlin"><code class="lang-kotlin"><strong>Gizo.app.gizoAnalysis.startSavingSession() 
</strong></code></pre>
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Stop saving session</mark>

While saving files is an essential aspect of many applications, it's important to consider the performance, battery, storage, security, and network implications associated with file saving operations. By optimizing and managing file saving processes, you can ensure a smooth user experience while efficiently utilizing system resources.

To stop saving files using MyTestSDK , use the following code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.stopSavingSession()
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Attach preview to camera</mark>

Preview View is a Custom View that displays the camera feed for CameraX's Preview use case. This class manages the preview Surface's lifecycle. It internally uses either a TextureView or SurfaceView to display the camera feed, and applies required transformations on them to correctly display the preview, this involves correcting their aspect ratio, scale and rotation.

So, to display camera a previewView should be attached as well.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.attachPreview(previewView)
```
{% endtab %}
{% endtabs %}

##

## Video Recording Options in MyTestSDK.

In Android Studio, the Preview feature allows developers to visualize and interact with the user interface (UI) of their Android app without the need to run the app on a physical device or emulator. It provides a real-time preview of how the UI will look and behave on different devices and screen sizes.

The Preview feature is primarily used in the XML layout editor, where developers design the UI of their app using XML markup or the visual drag-and-drop editor. With the Preview feature, developers can see a live rendering of the UI layout, including the arrangement of views, styles, themes, and other UI elements.

### <mark style="color:purple;">Lock Preview</mark>

Lock preview attaches the preview screen , while unlock preview detaches it .They are used to give developers the ability to display preview or not.

Once the Lock Preview feature is enabled, the preview will remain fixed to the chosen device configuration until the feature is disabled or the configuration is changed.

By using the Lock Preview feature, developers can maintain a focused and consistent preview display, allowing for more efficient UI design and testing in Android Studio.

To lock the preview using MyTestSDK , follow this line of code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.lockPreview()
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Unlock Preview</mark>

In Android Studio, the "Unlock Preview" feature is the counterpart to the "Lock Preview" feature in the XML layout editor's Preview pane. When the Unlock Preview feature is enabled, it allows the preview display to dynamically update and adapt to changes made to the XML layout or other settings.

To unlock the preview using MyTestSDK , follow this line of code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.unlockPreview(previewView)
```
{% endtab %}
{% endtabs %}





