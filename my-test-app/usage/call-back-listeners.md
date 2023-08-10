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

Callback listeners provide a way to handle user interactions and system events in Android applications. They allow you to customize the behavior of your app based on the events that occur, making your application more interactive and responsive to user actions.

Callback listeners allow you to register a listener object that will be notified when a specific event occurs. The listener object contains a set of callback methods that will be called by the system when the associated event occurs. These events include Analysis, IMU Sensors, GPS, Video, and Battery.

For using callback listeners we need to add this line of code in the Main activity above onCreate function:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
private val gizoAnalysis: GizoAnalysis = Gizo.app.gizoAnalysis
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">Analysis listener</mark>

When Analysis gets activated, these value parameters can be checked out:

<table><thead><tr><th width="237">Value-Parameters</th><th>Description</th></tr></thead><tbody><tr><td>result</td><td>It outputs an image that includes object detection &#x26; road lines.</td></tr><tr><td>fps</td><td>It provides the analysis time on the output image in milliseconds.</td></tr><tr><td>ttc</td><td></td></tr><tr><td>ttcStatus</td><td>It returns state <strong>danger</strong>, <strong>warning</strong>, and <strong>None</strong> based on the calculated formula in the TTC.</td></tr><tr><td>ttcDepthPtn</td><td></td></tr><tr><td>speed</td><td>The speed of the car the user is driving in.</td></tr><tr><td>gpsTime</td><td>The current time.</td></tr><tr><td>collisionThreshold </td><td>It provides a number that determines the specific status of danger, warning or none.</td></tr></tbody></table>



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



We can write a customized formula and calculate the ttc in Preview too.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcCalculator { depthPtn, speed, ttc ->
    ttc
}
```
{% endtab %}
{% endtabs %}



We can calculate the customized ttcStatus based on depthPtn, speed, collisionThreshold and ttc in Preview too.

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

When gps gets activated, these value parameters can be checked out:

<table><thead><tr><th width="264">Value-parameters</th><th>Description</th></tr></thead><tbody><tr><td>location</td><td>The location of the user</td></tr><tr><td>isGpsOn</td><td>To check whether gps is on or not</td></tr><tr><td>speedLimitKph</td><td>speed limit kilometer per hour</td></tr><tr><td>speedKph</td><td>speed kilometer per hour</td></tr></tbody></table>



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

When IMU gets activated, these value parameters can be checked out:

<table><thead><tr><th width="241">Value-parameters</th><th>Description</th></tr></thead><tbody><tr><td>accelerationSensorEvent</td><td>includes information such as Acceleration values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>gyroscopeSensorEvent</td><td>includes information such as Angular velocity values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>gravitySensorEvent</td><td>includes information such as Gravity values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>linearAccelerationEvent</td><td>includes information such as Acceleration values, Angular velocity values, Magnetic field values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>gyroscopeEvent</td><td>includes information such as Acceleration values, Angular velocity values, Magnetic field values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>garavityEvent</td><td>includes information such as Acceleration values, Angular velocity values, Magnetic field values, Timestamp &#x26; Accuracy or precision.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLinearAccelerationSensor={ accelerationSensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onGyroscopeSensor={ gyroscopeSensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onGravitySensor={ gravitySensorEvent->
    var sensorCallback = sensorEvent
}

gizoAnalysis.onImuSensor = { linearAccelerationEvent, gyroscopeEvent, gravityEvent ->
    var linearAccelerationCallBack = linearAccelerationEvent
    var gyroscopeCallBack = gyroscopeEvent
    var gravityCallBack = gravityEvent
}


```
{% endtab %}
{% endtabs %}







{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 gizoAnalysis.checkGravityAlignment { isAlign ->
}
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Video listener</mark>

When video gets activated, these value parameters can be checked out:

<table><thead><tr><th width="255">Value-parameters</th><th>Description</th></tr></thead><tbody><tr><td>isRecording</td><td>To check whether the camera is recording or not</td></tr><tr><td>previewAttached</td><td>To check whether the preview is attached or not</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kts
gizoAnalysis.onVideoRecordingStatus = { isRecording, previewAttached ->
}
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Battery listener</mark>

When battery gets activated, this value parameter can be checked out:

<table><thead><tr><th width="255">Value-parameter</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>To check what is the battery status: LOW_BATTERY_STOP, LOW-BATTERY_WARNING or NORMAL</td></tr></tbody></table>



Gain this parameter with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 gizoAnalysis.onBatteryStatusChange = { status ->
 
 }
```
{% endtab %}
{% endtabs %}
