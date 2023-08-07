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

# Call Back Listeners

Call back listeners allow you to register a listener object that will be notified when a specific event occurs. The listener object contains a set of callback methods that will be called by the system when the associated event occurs. These events include Analysis, IMU Sensors, GPS, Video and Battery.

For using call back listeners we need to add this line of code in Main activity above onCreate function:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
private val gizoAnalysis: GizoAnalysis = Gizo.app.gizoAnalysis
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">Analysis Call back listener</mark>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onAnalysisResult = { result, fps, ttc, ttcStatus, ttcDepthPtn, speed, gpsTime, ttcFrontPtn ->
    Log.d("result", "$result")
    Log.d("fps", "$fps")
    Log.d("ttc", "$ttc")
    Log.d("ttcStatus", "$ttcStatus")
    Log.d("ttcDepthPtn", "$ttcDepthPtn")
    Log.d("speed", "$speed")
    Log.d("gpsTime", "$gpsTime")
    Log.d("ttcFrontPtn", "$ttcFrontPtn")
}

gizoAnalysis.ttcCalculator { depthPtn, speed, ttc ->
    ttc
}

gizoAnalysis.ttcStatusCalculator { ttc, speed, collisionThreshold, ttcStatus ->
    Log.d("collisionThreshold", "$collisionThreshold")

    ttcStatus
}
```
{% endtab %}
{% endtabs %}

