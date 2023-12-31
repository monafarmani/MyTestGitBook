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

In this library, the aim is to analyze driving behavior and compute a series of data by using artificial intelligence to reduce the risk of accidents and other driving problems. As a result, the possibility of smarter and safer driving is provided to users.

There are some steps that must be taken to use Gizo Analysis

### <mark style="color:blue;">Step 1: Setting</mark>

First, there is a need to customize some behavior and functionality of our library by implementing some lines of code in [Gizo Analysis Setting](app-options-setting/gizoanalysissettings.md).

### <mark style="color:blue;">Step 2: Adding Model</mark>

In our SDK, we require accurate and efficient detection and localization of objects in images and video streams and also accurate and efficient estimation of the depth or distance of objects in a scene.

Object detection and depth estimation are crucial technologies in Android development that empower applications to perceive and understand their surroundings. By leveraging these capabilities, developers can enable their apps to identify objects within images or video streams and estimate the relative distances between objects in a scene.

\
**Object detection** plays a vital role in various Android applications, enabling tasks such as object recognition, tracking, and augmented reality

**Depth estimation** enables Android applications to perceive the relative distances between objects in a scene. This capability is valuable for tasks like depth-based segmentation, virtual reality, or 3D reconstruction.

Object detection and depth estimation can be implemented using machine learning models, such as those built with TensorFlow, and deployed using the TensorFlow Lite library.&#x20;



The model should be added to the assets of the app module.

Download the model from this link:&#x20;

[https://artificient-ai.s3.eu-central-1.amazonaws.com/artisense\_encrypted.data](https://artificient-ai.s3.eu-central-1.amazonaws.com/artisense\_encrypted.data)

### <mark style="color:blue;">Step 3: Loading Model</mark>

Loading a model allows the application to utilize the trained model's intelligence and perform complex tasks that go beyond traditional programming capabilities. By incorporating machine learning models into Android applications, developers can provide intelligent, data-driven features and functionalities to their users.

Add these lines of code in the Application class to load the model and receive the [listener](broken-reference) for different stats of loading, but the state of **LOADED** is essential for using Gizo Analysis completely.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
class Application : Application() {
    override fun onCreate() {
        super.onCreate()
        Gizo.app.loadModel()
    }
}
```
{% endtab %}
{% endtabs %}

<mark style="color:red;">**Note:**</mark> After these settings are done, a series of callbacks are triggered so that the corresponding output can be observed.



### <mark style="color:purple;">Start Gizo Analysis</mark>

To start using the SDK, we need to start Gizo Analysis. For this reason, we need a lifecycle like an activity or a fragment and implement some lines of code in the Activity.

Android components go through a series of states called the lifecycle. The Android framework provides a set of predefined methods that allow developers to perform specific actions or respond to events at different stages of the component’s lifecycle.

The typical lifecycle of an Android component includes the following states: Created, Started, Resumed, Paused, Stopped & Destroyed.

Based on the settings applied by the developer, a series of features will be added to the SDK.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 Gizo.app.gizoAnalysis.start(lifecycleOwner = this, onDone = {})
```
{% endtab %}
{% endtabs %}

**onDone is called when starting Gizo Analysis is completed.**

###

### <mark style="color:purple;">Stop Gizo Analysis</mark>

Whenever there is no longer a need for SDK, we should call the stop function to halt all ongoing operations within the library. These processes include video recording, GPS, IMU, analysis, and so on…&#x20;

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
  Gizo.app.gizoAnalysis.stop()
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Start Saving Session</mark>

Based on the settings we have applied, some files related to video, analysis, GPS, and IMU are saved.

Saving files in Android Studio has benefits like data persistence, offline accessibility, advanced analysis, sharing, backup, and tracking. It enhances the functionality, usability, and reliability of your app by ensuring the availability and integrity of important data.

To start saving files using Gizo SDK, use the following code, and receive the [listener](broken-reference) for session progress.

{% tabs %}
{% tab title="Kotlin" %}
<pre class="language-kotlin"><code class="lang-kotlin"><strong>Gizo.app.gizoAnalysis.startSavingSession() 
</strong></code></pre>
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Stop Saving Session</mark>

While saving files is an essential aspect of many applications, it’s important to consider the performance, battery, storage, security, and network implications associated with file-saving operations. By optimizing and managing file-saving processes, you can ensure a smooth user experience while efficiently utilizing system resources.

To stop saving files using Gizo SDK, use the following code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.stopSavingSession()
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">Attach Preview To Camera</mark>

Preview View is a Custom View that displays the camera feed for CameraX’s Preview use case. This class manages the preview of Surface’s lifecycle. After either a TextureView or a SurfaceView is used internally to display the camera feed, necessary transformations are applied to display the preview correctly. These transformations include correcting aspect ratio, scale, and rotation.

So, to display the camera, a previewView should be attached as well.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.attachPreview(previewView)
```
{% endtab %}
{% endtabs %}

##

## Analysis Options in Gizo SDK

In Android Studio, the Preview feature allows developers to visualize and interact with the user interface (UI) of their Android app without the need to run the app on a physical device or emulator. It provides a real-time preview of how the UI will look and behave on different devices and screen sizes.

The Preview feature is primarily used in the XML layout editor, where developers design the UI of their app using XML markup or the visual drag-and-drop editor. With the Preview feature, developers can see a live rendering of the UI layout, including the arrangement of views, styles, themes, and other UI elements.



### <mark style="color:purple;">Lock Preview</mark>

The lock preview attaches the preview screen, while the unlock preview detaches it. They are used to give developers the ability to preview or not.

Once the Lock Preview feature is enabled, the preview will remain fixed to the chosen device configuration until the feature is disabled or the configuration is changed.

By using the Lock Preview feature, developers can maintain a focused and consistent preview display, allowing for more efficient UI design and testing in Android Studio.

To lock the preview using Gizo SDK, follow this line of code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.lockPreview()
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Unlock Preview</mark>

In Android Studio, the “Unlock Preview” feature is the counterpart to the “Lock Preview” feature in the XML layout editor’s Preview pane. When the Unlock Preview feature is enabled, it allows the preview display to dynamically update and adapt to changes made to the XML layout or other settings.

To unlock the preview using Gizo SDK, follow this line of code:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Gizo.app.gizoAnalysis.unlockPreview(previewView)
```
{% endtab %}
{% endtabs %}





