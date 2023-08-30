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

Video settings on Gizo SDK refer to the various options and configurations that allow users to control and customize the video recording and playback experience. These settings can be accessed through the camera or video app on your mobile device.

Gizo video setting is used to customize some behavior and functionality of our library, including specifying the quality of video capturing and where to save video files.

To have access to video setting options, you need to add these lines of code in the Application class, onCreate function, inside Gizo.initialize.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
.videoSetting(
    GizoVideoSetting.Builder()
        .allowRecording(true)
        .quality(Quality.HD)
        .fileLocation(FileLocationPath.CACHE)
        .build()
)
```
{% endtab %}
{% endtabs %}

The `GizoVideoSetting` builder sets the video-related properties such as `quality` (setting the video quality to the HD quality), and `fileLocation` (specifying the file location path for storing the video files, in this case, set to the cache directory).

Finally, the build`()` method is called on the GizoAppOptions.Builder() instance to create a `GizoAppOptions` object with the configured video settings.   &#x20;

This code suggests that the `GizoAppOptions` class provides a way to specify various configuration options for the `Gizo` application, including video-related settings. The specific implementation and usage of `GizoAppOptions` would depend on the details of the `Gizo` application itself.



Here are the available options that can be set in videoSetting in the Application class:

<table><thead><tr><th width="240.33333333333331">Options</th><th width="213">Default Value</th><th>Description</th></tr></thead><tbody><tr><td><p>allowRecording(Boolean)</p><p></p></td><td>false</td><td>To activate recording video or not.</td></tr><tr><td>quality(Quality)</td><td>Quality.HD</td><td>To define the quality of video capturing.</td></tr><tr><td><p>fileLocation</p><p>(FileLocationPath)</p></td><td><p>FileLocationPath</p><p>.CACHE</p></td><td>To save video files in download or cache.</td></tr></tbody></table>

## <mark style="color:purple;">Different Video Qualities</mark>

Mobile devices typically support various video quality options, which may vary depending on the device's capabilities, operating system, and video recording settings. Here are some video quality options found in mobile devices:

* <mark style="color:green;">**SD**</mark> <mark style="color:green;">**(Standard Definition):**</mark> SD refers to videos recorded or played back at a standard resolution, typically 480p (854x480 pixels) or lower. SD videos have lower visual clarity and detail compared to higher-resolution options.
* <mark style="color:green;">**HD**</mark> <mark style="color:green;">**(High Definition):**</mark> HD videos offer improved quality and resolution compared to SD. They are typically recorded or played back at 720p (1280x720 pixels) or 1080p (1920x1080 pixels). HD videos provide sharper visuals and more detail.
* <mark style="color:green;">**FHD**</mark> <mark style="color:green;">**(Full HD):**</mark> FHD videos refer to videos with a resolution of 1080p (1920x1080 pixels). They offer even higher quality and clarity compared to HD videos. FHD is widely used as a standard for high-quality video content.
* <mark style="color:green;">**UHD**</mark> <mark style="color:green;">**(Ultra High Definition) or 4K:**</mark> UHD videos have a resolution of 2160p (3840x2160 pixels) or higher. UHD provides significantly higher detail, sharpness, and visual fidelity compared to lower-resolution options. It is commonly referred to as 4K due to its approximate horizontal pixel count of 4000.
* <mark style="color:green;">**Lowest Quality:**</mark> "Lowest" likely indicates the lowest available video quality setting on the device or application. The specific resolution and quality may vary depending on the device and settings, but it generally implies a lower resolution and reduced visual quality.
* <mark style="color:green;">**Highest Quality:**</mark> "Highest" generally refers to the maximum video quality supported by the device or application. It represents the best available resolution, sharpness, and visual fidelity that the device or application can handle.
