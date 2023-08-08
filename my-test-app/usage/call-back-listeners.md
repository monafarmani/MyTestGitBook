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

# Listeners

Call back listeners allow you to register a listener object that will be notified when a specific event occurs. The listener object contains a set of callback methods that will be called by the system when the associated event occurs. These events include Analysis, IMU Sensors, GPS, Video and Battery.

For using call back listeners we need to add this line of code in Main activity above onCreate function:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
private val gizoAnalysis: GizoAnalysis = Gizo.app.gizoAnalysis
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">Analysis listener</mark>

When Analysis gets activated, this value parameters can be checked out:

<table><thead><tr><th width="237">Value-Parameters</th><th>Description</th></tr></thead><tbody><tr><td>result</td><td>It outputs an image that includes object detection &#x26; road lines.</td></tr><tr><td>fps</td><td>It provides the analysis time on the output image in milliseconds.</td></tr><tr><td>ttc</td><td></td></tr><tr><td>ttcStatus</td><td>It returns states <strong>danger</strong>, <strong>warning</strong>, and <strong>None</strong> based on the calculated formula in the TTC.</td></tr><tr><td>ttcDepthPtn</td><td></td></tr><tr><td>speed</td><td>The speed of the car you are driving in.</td></tr><tr><td>gpsTime</td><td>The current time.</td></tr><tr><td>ttcFrontPtn</td><td></td></tr><tr><td>collisionThreshold </td><td>It provides a number that determines the specific status of danger, warning or none.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onAnalysisResult = { result, fps, ttc, ttcStatus,
ttcDepthPtn, speed, gpsTime, ttcFrontPtn ->
 
}
```
{% endtab %}
{% endtabs %}



We can write a customized formula and calculate the ttc in Preview.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcCalculator { depthPtn, speed, ttc ->
    ttc
}
```
{% endtab %}
{% endtabs %}



We can calculate the customized ttcStatus based on depthPtn, speed, collisionThreshold and ttc in Preview.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcStatusCalculator { ttc, speed, collisionThreshold, ttcStatus ->
  ttcStatus
}
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">GPS listener</mark>

When gps gets activated, this value parameters can be checked out:

<table><thead><tr><th width="264">Value-parameters</th><th>Description</th></tr></thead><tbody><tr><td>location</td><td>The location of the user</td></tr><tr><td>isGpsOn</td><td>To check wاether gps is on or not</td></tr><tr><td>speedLimitKph</td><td>speed limit kilometer per hour</td></tr><tr><td>speedKph</td><td>speed kilometer per hour</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLocationChange = { location, isGpsOn ->
   
}
gizoAnalysis.onSpeedChange = { speedLimitKph, speedKph ->
    
}
```
{% endtab %}
{% endtabs %}

###

### <mark style="color:purple;">IMU  listener</mark>

When IMU gets activated, this value parameters can be checked out:

<table><thead><tr><th width="290">Value-parameters</th><th></th></tr></thead><tbody><tr><td>linearAccelerationSensor</td><td></td></tr><tr><td>gyroscopeSensor</td><td></td></tr><tr><td>gravitySensor</td><td></td></tr></tbody></table>

Add the code to Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLinearAccelerationSensor={ sensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onGyroscopeSensor={ sensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onGravitySensor={ sensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onImuSensor = { linearAccelerationEvent, gyroscopeEvent, gravityEvent ->
    var linearAccelerationCallBack = linearAccelerationEvent
    var gyroscopeCallBack = gyroscopeEvent
    var gravityCallBack = gravityEvent
}

 gizoAnalysis.checkGravityAlignment { isAlign ->
}
```
{% endtab %}
{% endtabs %}

###



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
 gizoAnalysis.onBatteryStatusChange = { status ->
 }
```
{% endtab %}
{% endtabs %}
