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

## Overview

Callback listeners provide a way to handle user interactions and system events in Android applications. They allow you to customize the behavior of your app based on the events that occur, making your application more interactive and responsive to user actions.

Callback listeners allow you to register a listener object that will be notified when a specific event occurs. The listener object contains a set of callback methods that will be called by the system when the associated event occurs. These events include Analysis, IMU Sensors, GPS, Video, and Battery.



### <mark style="color:purple;">Session Status listener</mark>

As previously stated, based on the settings we have applied, some files related to video, analysis, GPS, and IMU are saved.

When the Start Session gets activated, these value parameters can be checked out:

<table><thead><tr><th width="370">Value-parameters</th><th width="127">Type</th><th>Description</th></tr></thead><tbody><tr><td>inProgress</td><td>Boolean</td><td>To check whether the camera is recording or not.</td></tr><tr><td>previewAttached</td><td>Boolean</td><td>To check whether the preview is attached or not.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kts
gizoAnalysis.onSessionStatus = { isRecording, previewAttached ->
}
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">Analysis listener</mark>

In our SDK, we require accurate and efficient detection and localization of objects in images and video streams and also accurate and efficient estimation of the depth or distance of objects in a scene and we gain these data with Gizo Analysis Setting.

When Analysis gets activated, these value parameters can be checked out:

<table><thead><tr><th width="203">Value-Parameters</th><th width="145">Type</th><th>Description</th></tr></thead><tbody><tr><td>result</td><td>Bitmap?</td><td>It outputs an image that includes object detection &#x26; road lines.</td></tr><tr><td>fps</td><td>String</td><td>It provides the analysis time on the output image in milliseconds.</td></tr><tr><td>ttc</td><td>Float?</td><td>Time to collision.</td></tr><tr><td>ttcStatus</td><td>TTCAlert</td><td>It returns state <strong>danger</strong>, <strong>warning</strong>, and <strong>None</strong> based on the calculated formula in the TTC.</td></tr><tr><td>ttcDepthPtn</td><td>String</td><td>The distance to the front car.</td></tr><tr><td>speed</td><td>Float?</td><td>The speed of the car the user is driving in.</td></tr><tr><td>gpsTime</td><td>String</td><td>The current time.</td></tr><tr><td>collisionThreshold </td><td>Float</td><td>It provides a number that determines the specific status of danger, warning, or none.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onAnalysisResult = { result, fps, ttc, ttcStatus,
ttcDepthPtn, speed, gpsTime ->
 
}
```
{% endtab %}
{% endtabs %}



We can write a customized formula and calculate the TTC in Preview too.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.ttcCalculator { depthPtn, speed, ttc ->
    ttc
}
```
{% endtab %}
{% endtabs %}



We can calculate the customized ttcStatus based on depthPtn, speed, collisionThreshold, and TTC in Preview too.

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

As mentioned earlier, this documentation provides instructions on enabling GPS, accessing location, speed limit, and speed.

When GPS gets activated, these value parameters can be checked out:

<table><thead><tr><th width="196">Value-parameters</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td>location</td><td>Location?</td><td>The location of the user.</td></tr><tr><td>isGpsOn</td><td>Boolean?</td><td>To check whether GPS is on or not.</td></tr><tr><td>speedLimitKph</td><td>Int?</td><td>speed limit kilometer per hour</td></tr><tr><td>speedKph</td><td>Int</td><td>speed kilometer per hour</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLocationChange = { location, isGpsOn ->
   
}
```
{% endtab %}
{% endtabs %}

###

{% tabs %}
{% tab title="Kotlin" %}
```
gizoAnalysis.onSpeedChange = { speedLimitKph, speedKph ->
    
}
```
{% endtab %}
{% endtabs %}

### <mark style="color:purple;">IMU listener</mark>

As previously mentioned, the IMU setting in MyTestSDK allows developers to utilize the sensors that make up the device’s IMU. The IMU typically consists of the accelerometer, gyroscope, and gravity.

When IMU gets activated, these value parameters can be checked out:

<table><thead><tr><th width="238">Value-parameters</th><th width="152">Type</th><th>Description</th></tr></thead><tbody><tr><td>accelerationSensorEvent</td><td>SensorEvent?</td><td>includes information such as Acceleration values, Timestamps &#x26; Accuracy, or precision.</td></tr><tr><td>gyroscopeSensorEvent</td><td>SensorEvent?</td><td>includes information such as Angular velocity values, timestamps &#x26; Accuracy, or precision.</td></tr><tr><td>gravitySensorEvent</td><td>SensorEvent?</td><td>includes information such as Gravity values, timestamps &#x26; Accuracy, or precision.</td></tr><tr><td>isAlign</td><td>Boolean</td><td>Whether the mobile device is in a landscape orientation or not.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLinearAccelerationSensor={ accelerationSensorEvent->
   
}
```
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="Kotlin" %}
```
gizoAnalysis.onGyroscopeSensor={ gyroscopeSensorEvent->
  
}
```
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="Kotlin" %}
```
gizoAnalysis.onGravitySensor={ gravitySensorEvent->
   
}
```
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="Kotlin" %}
```
gizoAnalysis.onImuSensor = { linearAccelerationEvent, gyroscopeEvent, gravityEvent ->

}
```
{% endtab %}
{% endtabs %}

Landscape screen orientation in mobile devices refers to a display mode where the screen is wider than it is tall, resembling the shape of a landscape. In this orientation, the device is typically held horizontally, with the longer edge of the screen parallel to the ground.

When a mobile device is in landscape orientation, the user interface and content on the screen adjust accordingly to make optimal use of the wider space. This orientation is commonly used for activities that benefit from a wider viewing area, such as watching videos, playing games, or viewing wide documents or images.

In MyTestSDK, if our mobile device is in landscape orientation, the listener calls back true. (isAlign would be true)

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 gizoAnalysis.checkGravityAlignment { isAlign ->
}
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Battery listener</mark>

Battery settings on the MyTestSDK library refer to the configuration and management options related to the device’s battery usage and performance. These settings allow users to monitor and control the battery usage of their mobile devices.

When the battery gets activated, this value parameter can be checked out:

<table><thead><tr><th width="184">Value-parameter</th><th width="142">Type</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>BatteryStatus</td><td>To check what is the battery status: LOW_BATTERY_STOP, LOW-BATTERY_WARNING, or NORMAL</td></tr></tbody></table>



Gain this parameter with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 gizoAnalysis.onBatteryStatusChange = { status ->
 
 }
```
{% endtab %}
{% endtabs %}
