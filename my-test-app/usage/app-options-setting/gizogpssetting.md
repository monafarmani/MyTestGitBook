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

# GizoGpsSetting

## Overview

The GPS settings in Gizo SDK allow developers to incorporate GPS functionality into their Android applications. This documentation provides instructions on enabling GPS, accessing location, speed limit, and speed.

Gizo GPS setting is used to customize some behavior and functionality of our library including specifying a loop of time for getting location in 1 second, maximum amount of initial wait time, where to save GPS file, the period of time that a GPS data row is saved in CSV file, the initial delay to save GPS data, the format to save date time and so on...

For this reason, add these lines of code in the Application class, onCreate function, inside Gizo.initialize to set the Gizo GPS Settings.

<mark style="color:red;">**Note:**</mark> we need to get [MAPBOX\_PUBLIC\_KEY](https://docs.mapbox.com/android/maps/guides/install/#configure-credentials) from Mapbox SDK.

{% tabs %}
{% tab title="Kotlin" %}
```kts
 .gpsSetting(
       GizoGpsSetting.Builder()
       .allowGps(true)
       .mapBoxKey("pk.eyJ1IjoibXlwbHVzIiwiYSI6ImNsYmMwbHBiNzFrcTQzcHFwaGdjb3RvcHIifQ.ysTPIV-rjUzxoBT4x_Zxww")
       .interval(1000L)
       .maxWaitTime(1000L)
       .withForegroundService(true)
       .saveCsvFile(true)
       .fileLocation(FileLocationPath.CACHE)
       .saveDataTimerPeriod(10L)
       .saveDataTimerInitialDelay(0L)
       .saveDataDateTimeFormat("yyyy-MM-dd'T'HH-mm-ss-SSS'Z'")
       .build())
```
{% endtab %}
{% endtabs %}

The `GizoGpsSetting` builder sets the GPS-related properties such as

* <mark style="color:blue;">`allowGps`</mark>`(true)`: Enabling GPS.
* <mark style="color:blue;">`mapBoxKey`</mark>`("pk.eyJ1IjoibXlwbHVzIiwiYSI6ImNsYmMwbHBiNzFrcTQzcHFwaGdjb3RvcHIifQ.ysTPIV-rjUzxoBT4x_Zxww")`: Providing the Mapbox API key for accessing Mapbox services.
* <mark style="color:blue;">`interval`</mark>`(1000L)`: Default interval between location updates which updates to 1000 milliseconds (1 second) here.
* <mark style="color:blue;">`maxWaitTime`</mark>`(1000L)`: Sets the maximum wait time in milliseconds for location updates. Locations determined at intervals but delivered in batch based on wait time. Batching is not supported by all engines.&#x20;
* <mark style="color:blue;">`withForegroundService`</mark>`(true)`: If you set withForegroundService to true and your apps targets Android 12 or higher, you should only invoke this method when the app is in foreground. This is dictated by background restrictions introduced in Android 12. See [https://developer.android.com/guide/components/foreground-services#background-start-restrictions](https://developer.android.com/guide/components/foreground-services#background-start-restrictions) for more info. withForegroundService - Boolean if set to false, foreground service will not be started and no notifications will be rendered, and no location updates will be available while the app is in the background. Default value is set to true.&#x20;
* <mark style="color:blue;">`saveCsvFile`</mark>`(true)`: Indicating that the GPS data should be saved to a CSV file.
* <mark style="color:blue;">`fileLocation`</mark>`(FileLocationPath.CACHE)`: Specifying the file location path for storing the GPS data CSV file (in this case, set to the cache directory).
* <mark style="color:blue;">`saveDataTimerPeriod`</mark>`(10L)`: Setting the period of saving GPS data to 10 milliseconds.



Finally, the `build()` method is called on the `GizoAppOptions.Builder()`instance to create a `GizoAppOptions` object with the configured GPS settings.

This code suggests that the `GizoAppOptions` class provides a way to specify various configuration options for the `Gizo` application, including GPS-related settings. The specific implementation and usage of `GizoAppOptions` would depend on the details of the `Gizo` application itself.



&#x20;Here are the available options that can be set in gpsSetting in the Application class:

<table><thead><tr><th width="253.33333333333331">Options</th><th width="196">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>allowGps(Boolean)</td><td>false</td><td>To allow access to GPS setting.</td></tr><tr><td><p>mapBoxKey</p><p>(String)</p></td><td>_____</td><td>The key was obtained from Mapbox.</td></tr><tr><td>interval(Long)</td><td>1000L</td><td>Default interval between location updates.</td></tr><tr><td>maxWaitTime(Long)</td><td>1000L</td><td>Sets the maximum wait time in milliseconds for location updates. Locations determined at intervals but delivered in batch based on wait time. Batching is not supported by all engines.  </td></tr><tr><td><p>withForegroundService</p><p>(Boolean)</p></td><td>true</td><td>If set to true, foreground service will be started, notifications will be rendered, and location updates will be available while the app is in the background. </td></tr><tr><td>saveCsvFile(Boolean)</td><td>false</td><td>To save CSV file or not.</td></tr><tr><td><p>fileLocation</p><p>(FileLocationPath)</p></td><td><p>FileLocationPath</p><p>.CACHE</p></td><td>To save GPS file in cache or download.</td></tr><tr><td><p>saveDataTimerPeriod</p><p>(Long)</p></td><td>10L</td><td>The period of time that a GPS data row is saved in CSV file.</td></tr></tbody></table>



