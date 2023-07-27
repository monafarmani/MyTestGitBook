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

# . App Options Setting

## Overview

The SDK provides several options that can be configured at the app level to customize its behavior. These options can be set in the Application class of your app.



## Setting App Options

To set app options for the SDK, you will need to create a new instance of the Application class in your app's module and set the desired options:

{% tabs %}
{% tab title="Kotlin" %}
<pre class="language-kotlin"><code class="lang-kotlin"><strong>class Application : Application() {
</strong>    override fun onCreate() {
        super.onCreate()

        Gizo.initialize(
            this,
            GizoApp.GizoAppOptions.Builder()
                .debug(true)
                .folderName("GizoSample")
                .analysisSetting(GizoAnalysisSettings.Builder().build())
                .imuSetting(GizoImuSetting.Builder().build())
                .gpsSetting(GizoGpsSetting.Builder().build())
                .videoSetting(GizoVideoSetting.Builder().build())
                .batterySetting(GizoBatterySetting.Builder().build())
                .build()
        )
    }
}
</code></pre>
{% endtab %}
{% endtabs %}

In the example above, we initialize the sdk instance as before, and then create a new instance of the GizoAppOptions class and set the desired options using the builder pattern.



## Available Options

&#x20;Here are the available options that can be set in the Application class:



<table><thead><tr><th width="336.3333333333333">Option</th><th width="137">Default Value</th><th>Description</th></tr></thead><tbody><tr><td>debug(Boolean)</td><td>true</td><td>set to enable debugging log feature.</td></tr><tr><td>folderName(String)</td><td>"Gizo"</td><td>set to save files in a download folder with this name.</td></tr><tr><td>analysisSetting(<a href="gizoanalysissettings.md">GizoAnalysisSettings</a>)</td><td>null</td><td>set to activate analyzing model &#x26; main export of the sdk.</td></tr><tr><td>imuSetting(<a href="gizoimusetting.md">GizoImuSetting</a>)</td><td>null</td><td>set to activate some sensors such as LinearAccelerationSensor , GyroscopeSensor &#x26; GravitySensor and get call backs.</td></tr><tr><td>gpsSetting(<a href="gizogpssetting.md">GizoGpsSetting</a>)</td><td>null</td><td>set to provide location information to use in speed limit.</td></tr><tr><td>videoSetting(<a href="gizovideosetting.md">GizoVideoSetting</a>)</td><td>null</td><td>set the video export.</td></tr><tr><td>batterySetting(<a href="gizobatterysetting.md">GizoBatterySetting</a>)</td><td>null</td><td>set the required implementation when the battery is in different status.</td></tr></tbody></table>
