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

# GizoAnalysisSetting

## Overview

Gizo Analysis setting is used to customize some behavior and functionality of our library including specifying the processing method on the model, the distance from the windshield to the hood of the car, the initial amount of timer, time to collision number (TTC), where to save the file, what period interval the data should be saved or sent, and where to save matrix file.

To do this task, add these lines of code in the Application class to set the Gizo Analysis Settings:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
.analysisSetting(
    GizoAnalysisSettings.Builder()
        .allowAnalysis(true)
        .modelName("arti_sense.data")
        .loadDelegate(AnalysisDelegateType.Auto)
        .collisionThreshold(0.5f)
        .tailgatingThreshold(1.0f)
        .saveTtcCsvFile(true)
        .ttcFileLocation(FileLocationPath.CACHE)
        .saveDataTimerPeriod(10L)
        .saveMatrixFile(true)
        .matrixFileLocation(FileLocationPath.CACHE)
        .build()
)
```
{% endtab %}
{% endtabs %}

<mark style="color:red;">**Note:**</mark> To enable GizoAnalysisSettings, it is essential to activate [GPS Setting](gizogpssetting.md).&#x20;



The `GizoAnalysisSettings` builder sets the analysis-related properties such as

* <mark style="color:blue;">`allowAnalysis`</mark>`(true)`: Enabling the analysis feature.
* <mark style="color:blue;">`modelName`</mark>`("arti_sense.data")`: Providing the name of the model to be used for analysis.
* <mark style="color:blue;">`loadDelegate`</mark>`(AnalysisDelegateType.Auto)`: Specifying the analysis delegate type as "Auto", which determines the best delegate based on the device's capabilities.
* <mark style="color:blue;">`collisionThreshold`</mark>`(0.5f)`: Setting the collision threshold value for analysis.

<mark style="color:red;">**Note:**</mark> collisionThreshold parameter can be either Float or ThresholdType.None. If ThresholdType.None is chosen as the parameter, collision wouldn't be considered in the ttc status calculation.

* <mark style="color:blue;">`tailgatingThreshold`</mark>`(1.0f)`: Setting the tailgating threshold value for analysis.

<mark style="color:red;">**Note:**</mark> tailgatingThreshold parameter can be either Float or ThresholdType.None. If ThresholdType.None is chosen as the parameter, tailgating wouldn't be considered in the ttc status calculation.

* <mark style="color:blue;">`saveTtcCsvFile`</mark>`(true)`: Indicating that the TTC data should be saved to a file.
* <mark style="color:blue;">`ttcFileLocation`</mark>`(FileLocationPath.CACHE)`: Specifying the file location path for storing Time-to-Collision (TTC) data (in this case, set to the cache directory).
* <mark style="color:blue;">`saveDataTimerPeriod`</mark>`(30L)`: Setting the period of the TTC data timer to 30 milliseconds.
* <mark style="color:blue;">`saveMatrixFile`</mark>`(true)`: Indicating that the analysis matrix file should be saved.
* <mark style="color:blue;">`matrixFileLocation`</mark>`(FileLocationPath.CACHE)`: Specifying the file location path for storing the Matrix of the camera (in this case, set to the cache directory).&#x20;

Finally, the `build()` method is called on the `GizoAppOptions.Builder()` instance to create a `GizoAppOptions` object with the configured analysis settings.



&#x20;Here are the available options that can be set in analysisSetting in the Application class:

<table><thead><tr><th width="240.33333333333331">Options</th><th width="207">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>allowAnalysis(Boolean)</td><td>false</td><td><p>To allow to use it or not.</p><p> </p></td></tr><tr><td>modelName(String)</td><td>""</td><td>A name that corresponds to this model's name.</td></tr><tr><td><p>loadDelegate</p><p>(AnalysisDelegateType)</p></td><td><p>AnalysisDelegateType</p><p>.Auto</p></td><td>To specify the processing method on the model e.g. <strong>CPU</strong>, <strong>GPU</strong>, <strong>NNAPI</strong>, and <strong>AUTO</strong>.</td></tr><tr><td><p>collisionThreshold</p><p>(Float or ThresholdType)</p></td><td>0.5f</td><td>The number that is used in the TTC calculations collision.</td></tr><tr><td><p>tailgatingThreshold</p><p>(Float or ThresholdType)</p></td><td>1.0f</td><td>The number that is used in the TTC calculations tailgating.</td></tr><tr><td>saveTtcCsvFile(Boolean)</td><td>false</td><td>Should the file of TTC be saved in CSV format or not.</td></tr><tr><td><p>ttcFileLocation</p><p>(FileLocationPath)</p></td><td><p>GizoFileLocationPath</p><p>.CACHE</p></td><td>Where the file should be saved, in the cache or download.</td></tr><tr><td><p>ttcDataTimerPeriod</p><p>(Long)</p></td><td>30L</td><td>To specify in what period of time interval the data should be saved and sent.</td></tr><tr><td><p>saveMatrixFile</p><p>(Boolean)</p></td><td>false</td><td>Should it save the matrix file that is created based on the camera resolution or not?</td></tr><tr><td><p>matrixFileLocation</p><p>(FileLocationPath)</p></td><td><p>GizoFileLocationPath</p><p>.CACHE</p></td><td>Where to save matrix file.</td></tr></tbody></table>



###
