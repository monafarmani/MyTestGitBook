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

# GizoImuSetting

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
.imuSetting(
    GizoImuSetting.Builder()
        .allowLinearAccelerationSensor(true)
        .allowGravitySensor(true)
        .saveCsvFile(true)
        .imuDataTimerPeriod(5000L)
        .build()
)
```
{% endtab %}
{% endtabs %}

```
 val allowLinearAccelerationSensor: Boolean,
    val allowGyroscopeSensor: Boolean,
    val allowGravitySensor: Boolean,
    val saveCsvFile: Boolean,
    val fileLocation: GizoFileLocationPath,
    val imuDataTimerPeriod: Long,
    val imuDataTimerInitialDelay: Long,
    val saveDataDateTimeFormat: String,
```

Here are the available options that can be set in imuSetting in the Application class:



<table><thead><tr><th width="286.3333333333333">Options</th><th>Default Value</th><th>Descriptions</th></tr></thead><tbody><tr><td><p>allowLinearAccelerationSensor</p><p>(Boolean)</p></td><td></td><td></td></tr><tr><td><p>allowGravitySensor</p><p>(Boolean)</p></td><td></td><td></td></tr><tr><td><p>saveCsvFile</p><p>(Boolean)</p></td><td></td><td></td></tr><tr><td><p>fileLocation</p><p>(GizoFileLocationPath)</p></td><td></td><td></td></tr><tr><td>imuDataTimerPeriod(Long)</td><td></td><td></td></tr><tr><td>imuDataTimerInitialDelay(Long)</td><td></td><td></td></tr><tr><td><p>saveDateDateTimeFormat</p><p>(String)</p></td><td></td><td></td></tr></tbody></table>

