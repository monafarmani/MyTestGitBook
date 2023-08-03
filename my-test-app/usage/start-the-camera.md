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

# Start The Camera

To start using the SDK we need to [start the camera ](start-the-camera.md), for this reason we need a lifecycle like an activity or a fragment and implement these lines of code in the Activity: first we start the camera, second preview is attached.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 Gizo.app.gizoAnalysis.startCamera(lifecycleOwner = this, onDone = {})
```
{% endtab %}
{% endtabs %}

