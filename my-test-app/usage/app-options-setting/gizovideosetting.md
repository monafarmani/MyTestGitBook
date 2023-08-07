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
