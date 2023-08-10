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

# GizoVideoSetting

## Overview

Battery settings on MyTestSDK library refer to the configuration and management options related to the device’s battery usage and performance. These settings allow users to monitor and control the battery usage of their mobile devices.

Gizo battery setting is used to customize some behavior and functionality of our library, including specifying the minimum percentage of battery charge that Analysis options can be implemented, The minimum percentage of battery charge that Recording video can be implemented, A loop of time for getting battery status in 1 second, and so on ...

To have access to battery setting options, you need to add these lines of code in the Application class, onCreate function, inside Gizo.initialize.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
.videoSetting(
    GizoVideoSetting.Builder()
        .quality(Quality.LOWEST)
        .build()
)
```
{% endtab %}
{% endtabs %}



Here are the available options that can be set in videoSetting in the Application class:

<table><thead><tr><th width="227.33333333333331">Options</th><th width="213">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>quality(Quality)</td><td>Quality.HD</td><td>To define the quality of video capturing.</td></tr><tr><td><p>fileLocation</p><p>(GizoFileLocationPath)</p></td><td><p>GizoFileLocationPath</p><p>.CACHE</p></td><td>To save video files in download or cache.</td></tr></tbody></table>

