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

# GizoAnalysisSettings

## overview

In our sdk we require accurate and efficient detection and localization of objects in images and video streams and also require accurate and efficient estimation of the depth or distance of objects in a scene.

In Android Studio, object detection and depth estimation can be implemented using machine learning models, such as those built with TensorFlow, and deployed using the TensorFlow Lite library.&#x20;

### <mark style="color:purple;">Step 1: Adding model</mark>

the model should be added in assets of app module.

Download the model from this link:&#x20;



### <mark style="color:purple;">Step 2: Add Gizo Analysis Settings</mark>

Add these lines of code in Application class to set the Gizo Analysis Settings&#x20;

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
class Application : Application() {
    override fun onCreate() {
        super.onCreate()

        Gizo.initialize(
            this,
            GizoApp.GizoAppOptions.Builder()
                .debug(true)
                .folderName("GizoSample")
                .analysisSetting(GizoAnalysisSettings.Builder()
                
                //add these lines
                
                    .allow(true)
                    .modelName("arti_sense.tflite")
                    .loadDelegate(GizoAnalysisSettings.AnalysisDelegateType.Auto)
                    .carHeight(1.6)
                    .saveMatrixFile(true)
                    .saveTTcFile(true)
                    .build())
                .imuSetting(GizoImuSetting.Builder().build())
                .gpsSetting(GizoGpsSetting.Builder().build())
                .videoSetting(GizoVideoSetting.Builder().build())
                .batterySetting(GizoBatterySetting.Builder().build())
                
                .build()
        )
    }
   }
```
{% endtab %}
{% endtabs %}



&#x20;Here are the available options that can be set in analysisSetting in  the Application class:



<table><thead><tr><th width="358.3333333333333">Options</th><th>Default Value</th><th>Description</th></tr></thead><tbody><tr><td>allow(Boolean)</td><td></td><td></td></tr><tr><td>modelName(String)</td><td></td><td></td></tr><tr><td>loadDelegate(AnalysisDelegateType)</td><td></td><td></td></tr><tr><td>carHeight(Double)</td><td></td><td></td></tr><tr><td>collisionThreshold(Float)</td><td></td><td></td></tr><tr><td>saveTTcFile(Boolean)</td><td></td><td></td></tr><tr><td>ttcFileLocation(GizoFileLocationPath)</td><td></td><td></td></tr><tr><td>ttcDataTimerPeriod(Long)</td><td></td><td></td></tr><tr><td>ttcDataTimerInitialDelay(Long)</td><td></td><td></td></tr><tr><td>saveMatrixFile(Boolean)</td><td></td><td></td></tr><tr><td>matrixFileLocation(GizoFileLocationPath)</td><td></td><td></td></tr></tbody></table>



### <mark style="color:purple;">Step 3: Loading model</mark>

Add these lines of code in Application class to load the model and receive the listener for different status of loading such as LOADING, LOADED, FAILED, NOT\_LOADED



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
        
        // add these line of code

        Gizo.app.setLoadModelObserver { status ->
            Log.d("LoadModelStatus", "status:" + status.name)
        }

        Gizo.app.loadModel()
    }
}
```
{% endtab %}
{% endtabs %}

