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

When Analysis gets activated, this call backs can be checked out,

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onAnalysisResult = { result, fps, ttc, ttcStatus,
ttcDepthPtn, speed, gpsTime, ttcFrontPtn ->
 
}
```
{% endtab %}
{% endtabs %}

## Value Parameters

<table><thead><tr><th width="260">Value-Parameters</th><th>Description</th></tr></thead><tbody><tr><td>result</td><td>It outputs an image that includes object detection &#x26; road lines.</td></tr><tr><td>fps</td><td>It provides the analysis time on the output image in milliseconds.</td></tr><tr><td>ttc</td><td></td></tr><tr><td>ttcStatus</td><td>It returns states <strong>danger</strong>, <strong>warning</strong>, and <strong>None</strong> based on the calculated formula in the TTC.</td></tr><tr><td>ttcDepthPtn</td><td></td></tr><tr><td>speed</td><td>The speed of the car you are driving in.</td></tr><tr><td>gpsTime</td><td>The current time.</td></tr><tr><td>ttcFrontPtn</td><td></td></tr></tbody></table>



We can write a customized formula and calculate the ttc.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcCalculator { depthPtn, speed, ttc ->
    ttc
}
```
{% endtab %}
{% endtabs %}



We can calculate the customized ttcStatus based depthPtn, speed, and ttc.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcStatusCalculator { ttc, speed, collisionThreshold, ttcStatus ->
  ttcStatus
}
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">IMU Call back listener</mark>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLinearAccelerationSensor={ sensorEvent->
    var sensorCallback = sensorEvent
    Log.d("onLinearAccelerationSensor", "$sensorEvent")
}

gizoAnalysis.onGyroscopeSensor={ sensorEvent->
    var sensorCallback = sensorEvent
    Log.d("onGyroscopeSensor", "$sensorEvent")
}

gizoAnalysis.onGravitySensor={ sensorEvent->
    var sensorCallback = sensorEvent
    Log.d("onGravitySensor", "$sensorEvent")
}

gizoAnalysis.onImuSensor = { linearAccelerationEvent, gyroscopeEvent, gravityEvent ->
    var linearAccelerationCallBack = linearAccelerationEvent
    var gyroscopeCallBack = gyroscopeEvent
    var gravityCallBack = gravityEvent
    Log.d("linearAccelerationEvent", "$linearAccelerationEvent")
    Log.d("gyroscopeEvent", "$gyroscopeEvent")
    Log.d("gravityEvent", "$gravityEvent")
}

 gizoAnalysis.checkGravityAlignment { isAlign ->
        Log.d("checkGravityAlignment", "$isAlign")
}
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">GPS Call back listener</mark>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}

{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Video Call back listener</mark>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kts
gizoAnalysis.onVideoRecordingStatus = { isRecording, previewAttached ->
    Log.d("isRecording", "$isRecording")
    Log.d("previewAttached", "$previewAttached")
}
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Battery Call back listener</mark>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Log.d("batteryStatus11", "${gizoAnalysis.batteryLastStatus}")
```
{% endtab %}
{% endtabs %}
