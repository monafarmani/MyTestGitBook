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

# ✏ Change Log

## <mark style="color:purple;">v0.1.1</mark>

### <mark style="color:blue;">Breaking Changes</mark>  ⚠️

* Replace style related enum classes with regular classes.
* Migrate from `android.app.AlertDialog` to `androidx.appcompat.app.AlertDialog` for attribution plugin.
* Rename `MapboxMap.subscribeStyleImageUnused` to `MapboxMap.subscribeStyleImageRemoveUnused`.

### <mark style="color:blue;">Features</mark> ✨ <mark style="color:blue;">And Improvements</mark> 🏁

* Introduce experimental `MapboxMapRecorder` allowing to record and replay custom scenarios.
* New compose example `MulitDisplayActiviy` ported from XML test app.
* Add Mapbox Privacy Policy to attribution links.

### <mark style="color:blue;">Bug Fixes</mark> 🐞

* Fix the bug when anchor was not reset after gestures leading to an unexpected map camera animation result with incorrect `CameraState.center`.
* Fix a rounding error when point lies at the edge of the screen by using `rountToInt` for limiting `MapboxMap.pixelsForCoordinates` to the bounds of MapView.
* Fix the bug when `MapboxMap.getStyle` returned NULL if `MapboxMap.subscribeStyleLoaded` called before `MapboxMap.loadStyle`.
* Fix NPE when animating edge insets types (e.g. map padding).
* Reduce segment overlap in flood lighting to improve rendering performance.
* Enable offline support for the Standard style.
* Add wireframe rendering debug feature `MapDebugOptions.LAYERS3_DWIREFRAME` and `MapDebugOptions.LAYERS2_DWIREFRAME`.

### <mark style="color:blue;">Dependencies</mark>

Update dependencies:

<table><thead><tr><th width="254">Dependency</th><th width="236.33333333333331">Before</th><th>After</th></tr></thead><tbody><tr><td>NDK</td><td>21.4.7075529</td><td>23.2.8568313</td></tr><tr><td>gl-native</td><td>11.0.0-beta.2</td><td>11.0.0-beta.3</td></tr><tr><td>common</td><td>24.0.0-beta.2</td><td>24.0.0-beta.3</td></tr></tbody></table>

##

## <mark style="color:purple;">v0.1.0</mark>

### <mark style="color:blue;">Features</mark> ✨

* Introduce Gizo Analysis allowing to to gain some data based on the image caught from the camera, and Perform calculations based on data.
* Introduce Gizo GPS allowing to provide location information to access location, speed limit, and speed.
* Add Gizo IMU to utilize the sensors that make up the device's IMU. The IMU typically consists of the **accelerometer**, **gyroscope, gravity,** and **magnetic**.
* Introduce Gizo video allowing utilization of video-related features.
* Add Gizo battery to monitor and control the battery usage of their mobile devices.
* Add Gizo orientation activating the gravity sensor.

### <mark style="color:blue;">Dependencies</mark>

<table><thead><tr><th width="300">Dependency</th><th width="187.33333333333331">Before</th><th>After</th></tr></thead><tbody><tr><td>CameraX</td><td>________</td><td>1.3.0-beta01</td></tr><tr><td>MapBox</td><td>________</td><td>10.10.0</td></tr><tr><td><p>Mapbox services</p><p>Mapbox core  </p><p>Mapbox geojson</p></td><td>________</td><td>6.9.0</td></tr><tr><td>annotation</td><td>________</td><td>1.5.0</td></tr><tr><td>Mapbox navigation</td><td>________</td><td>2.10.0</td></tr><tr><td>OpenCV</td><td>________</td><td>3.4.1</td></tr><tr><td><p>Tensorflow lite </p><p>Tensorflow lite gpu </p><p>Tensorflow lite gpu  api</p></td><td>________</td><td>2.11.0</td></tr><tr><td>Tensorflow lite support</td><td>________</td><td>0.4.3</td></tr></tbody></table>
