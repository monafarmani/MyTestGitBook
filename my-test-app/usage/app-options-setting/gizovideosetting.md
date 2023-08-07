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

In MyTestSdk library, video settings refer to the configuration and utilization of video-related features and components within an Android application. Video settings typically involve tasks such as capturing video from the device's camera, playing video files, or streaming video content.

To have access to video options, you need to add these lines of code in Application class , onCreate function , inside Gizo.initialize.

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

<table><thead><tr><th width="227.33333333333331">Options</th><th width="213">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>quality(Quality)</td><td>Quality.HD</td><td>To define the quality of video capturing.</td></tr><tr><td><p>fileLocation</p><p>(GizoFileLocationPath)</p></td><td><p>GizoFileLocationPath</p><p>.CACHE</p></td><td>To save video file in download or cache.</td></tr></tbody></table>

