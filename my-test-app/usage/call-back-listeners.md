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



### <mark style="color:purple;">Analysis listener</mark>

When Analysis gets activated, these value parameters can be checked out:

<table><thead><tr><th width="203">Value-Parameters</th><th width="145">Type</th><th>Description</th></tr></thead><tbody><tr><td>result</td><td>Bitmap?</td><td>It outputs an image that includes object detection &#x26; road lines.</td></tr><tr><td>fps</td><td>String</td><td>It provides the analysis time on the output image in milliseconds.</td></tr><tr><td>ttc</td><td>Float?</td><td></td></tr><tr><td>ttcStatus</td><td>TTCAlert</td><td>It returns state <strong>danger</strong>, <strong>warning</strong>, and <strong>None</strong> based on the calculated formula in the TTC.</td></tr><tr><td>ttcDepthPtn</td><td>String</td><td></td></tr><tr><td>speed</td><td>Float?</td><td>The speed of the car the user is driving in.</td></tr><tr><td>gpsTime</td><td>String</td><td>The current time.</td></tr><tr><td>collisionThreshold </td><td>Float</td><td>It provides a number that determines the specific status of danger, warning, or none.</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onAnalysisResult = { result, fps, ttc, ttcStatus,
ttcDepthPtn, speed, gpsTime ->
 
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

<table><thead><tr><th width="196">Value-parameters</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td>location</td><td>Locatoin?</td><td>The location of the user</td></tr><tr><td>isGpsOn</td><td>Boolean?</td><td>To check whether gps is on or not</td></tr><tr><td>speedLimitKph</td><td>Int?</td><td>speed limit kilometer per hour</td></tr><tr><td>speedKph</td><td>Int</td><td>speed kilometer per hour</td></tr></tbody></table>



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

<table><thead><tr><th width="238">Value-parameters</th><th width="152">Type</th><th>Description</th></tr></thead><tbody><tr><td>accelerationSensorEvent</td><td>SensorEvent?</td><td>includes information such as Acceleration values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>gyroscopeSensorEvent</td><td>SensorEvent?</td><td>includes information such as Angular velocity values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>gravitySensorEvent</td><td>SensorEvent?</td><td>includes information such as Gravity values, Timestamp &#x26; Accuracy or precision.</td></tr><tr><td>isAlign</td><td>Boolean</td><td></td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
gizoAnalysis.onLinearAccelerationSensor={ accelerationSensorEvent->
   
}

gizoAnalysis.onGyroscopeSensor={ gyroscopeSensorEvent->
  
}

gizoAnalysis.onGravitySensor={ gravitySensorEvent->
   
}

gizoAnalysis.onImuSensor = { linearAccelerationEvent, gyroscopeEvent, gravityEvent ->

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

<table><thead><tr><th width="192">Value-parameters</th><th width="127">Type</th><th>Description</th></tr></thead><tbody><tr><td>isRecording</td><td>Boolean</td><td>To check whether the camera is recording or not</td></tr><tr><td>previewAttached</td><td>Boolean</td><td>To check whether the preview is attached or not</td></tr></tbody></table>



Gain these parameters with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kts
gizoAnalysis.onSessionStatus = { isRecording, previewAttached ->
}
```
{% endtab %}
{% endtabs %}



### <mark style="color:purple;">Battery listener</mark>

When battery gets activated, this value parameter can be checked out:

<table><thead><tr><th width="184">Value-parameter</th><th width="106">Type</th><th>Description</th></tr></thead><tbody><tr><td>status</td><td>String</td><td>To check what is the battery status: LOW_BATTERY_STOP, LOW-BATTERY_WARNING or NORMAL</td></tr></tbody></table>



Gain this parameter with the codes below in Preview

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 gizoAnalysis.onBatteryStatusChange = { status ->
 
 }
```
{% endtab %}
{% endtabs %}
