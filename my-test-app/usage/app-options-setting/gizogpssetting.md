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

# GizoGpsSetting

Add these lines of code in Application class to set the Gizo GPS Settings&#x20;



{% tabs %}
{% tab title="Kotlin" %}
```kts
class Application : Application() {
    override fun onCreate() {
        super.onCreate()

        Gizo.initialize(
            this,
            GizoApp.GizoAppOptions.Builder()
                .debug(true)
                .folderName("GizoSample")
                .analysisSetting(GizoAnalysisSettings.Builder()
                    .allow(true)
                    .modelName("arti_sense.tflite")
                    .loadDelegate(GizoAnalysisSettings.AnalysisDelegateType.Auto)
                    .carHeight(1.6)
                    .saveMatrixFile(true)
                    .saveTTcFile(true)
                    .build())
                    
                    //Add these lines 
                    
                .gpsSetting(
                    GizoGpsSetting.Builder()
                        .allow(true)
                        .mapBoxKey("pk.eyJ1IjoibXlwbHVzIiwiYSI6ImNsYmMwbHBiNzFrcTQzcHFwaGdjb3RvcHIifQ.ysTPIV-rjUzxoBT4x_Zxww")
                        .saveCsvFile(true)
                        .build())
                     //   
                        
                .imuSetting(GizoImuSetting.Builder().build())
                .videoSetting(GizoVideoSetting.Builder().build())
                .batterySetting(GizoBatterySetting.Builder().build())
                .build()
        )

        Gizo.app.setLoadModelObserver { status ->
            Log.d("LoadModelStatus", "status:" + status.name)
        }

        Gizo.app.loadModel()
    }
}
```
{% endtab %}
{% endtabs %}

&#x20;Here are the available options that can be set in gpsSetting in  the Application class:

<table><thead><tr><th width="310.3333333333333">Options</th><th width="312">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>allow(Boolean)</td><td>false</td><td></td></tr><tr><td>mapBoxKey(String?)</td><td>_____</td><td></td></tr><tr><td>interval(Long)</td><td>1000L</td><td></td></tr><tr><td>maxWithTime(Long)</td><td>1000L</td><td></td></tr><tr><td>withForeGroundService(Boolean)</td><td>true</td><td></td></tr><tr><td>saveCsvFile(Boolean)</td><td>false</td><td></td></tr><tr><td>fileLocation(GizoFileLocationPath)</td><td>GizoFileLocationPath.CACHE</td><td></td></tr><tr><td>savePeriod(Long)</td><td>10L</td><td></td></tr><tr><td>saveInitialDelay(Long)</td><td>0L</td><td></td></tr><tr><td>saveDateTimeFormat(String)</td><td>"yyyy-MM-dd'T'HH-mm-ss-SSS'Z'"</td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



