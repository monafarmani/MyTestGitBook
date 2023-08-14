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

# GizoBatterySetting

## Overview

&#x20;Battery settings on MyTestSDK library refer to the configuration and management options related to the device’s battery usage and performance. These settings allow users to monitor and control the battery usage of their mobile devices.

Gizo battery setting is used to customize some behavior and functionality of our library, including specifying the minimum percentage of battery charge that Analysis options can be implemented, The minimum percentage of battery charge that Recording video can be implemented, A loop of time for getting battery status in 1 second, and so on ...

To have access to battery setting options, you need to add these lines of code in the Application class, onCreate function, inside Gizo.initialize.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
.batterySetting(
    GizoBatterySetting.Builder()
         .checkBattery(true)
         .lowBatteryLimit(25f)
         .lowBatteryStop(15f)
         .interval(5000L)
        .build()
)
```
{% endtab %}
{% endtabs %}



Here are the available options that can be set in batterySetting in the Application class:

<table><thead><tr><th width="252">Options</th><th width="167.33333333333331">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>checkBattery(Boolean)</td><td>false</td><td>To allow to check the battery status or not.</td></tr><tr><td>lowBatteryLimit(Float)</td><td>25f</td><td>The minimum percentage of battery charge that Analysis options can be implemented.</td></tr><tr><td>lowBatteryStop(Float)</td><td>15f</td><td>The minimum percentage of battery charge that Recording video can be implemented.</td></tr><tr><td>interval(Long)</td><td>5000L</td><td>A loop of time for getting battery status in 1 second.</td></tr></tbody></table>
