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

# Call back listeners

Call back listeners allow you to register a listener object that will be notified when a specific event occurs. The listener object contains a set of callback methods that will be called by the system when the associated event occurs. These events include Analysis, IMU Sensors, GPS, Video and Battery.

For using call back listeners we need to add this line of code in Main activity above onCreate function

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
private val gizoAnalysis: GizoAnalysis = Gizo.app.gizoAnalysis
```
{% endtab %}
{% endtabs %}

### Analysis Call back listener

