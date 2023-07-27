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

