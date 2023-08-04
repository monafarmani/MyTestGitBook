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
          .allowGyroscopeSensor(true)
          .saveCsvFile(true)
          .imuDataTimerPeriod(5000L)
          .build()
                )
```
{% endtab %}
{% endtabs %}



Here are the available options that can be set in imuSetting in the Application class:

<table><thead><tr><th width="286.3333333333333">Options</th><th width="198">Default Value</th><th>Descriptions</th></tr></thead><tbody><tr><td><p>allowLinearAccelerationSensor</p><p>(Boolean)</p></td><td>false</td><td>To activate linear acceleration sensor or not.</td></tr><tr><td><p>allowGyroscopeSensor</p><p>(Boolean)</p></td><td>false</td><td>To activate gyroscpoe sensor or not.</td></tr><tr><td><p>allowGravitySensor</p><p>(Boolean)</p></td><td>false</td><td>To activate gravity sensor or not.</td></tr><tr><td><p>saveCsvFile</p><p>(Boolean)</p></td><td>false</td><td>To save CSV file or not.</td></tr><tr><td><p>fileLocation</p><p>(GizoFileLocationPath)</p></td><td><p>GizoFileLocationPath</p><p>.CACHE</p></td><td>To save imu file in download or cache.</td></tr><tr><td>imuDataTimerPeriod(Long)</td><td>10L</td><td></td></tr><tr><td>imuDataTimerInitialDelay(Long)</td><td>0L</td><td></td></tr><tr><td><p>saveDateDateTimeFormat</p><p>(String)</p></td><td><p>"yyyy-MM-dd</p><p>'T'HH-mm-ss-SSS'Z'"</p></td><td></td></tr></tbody></table>

