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

# 🚀 . Getting Started

#### To use My Test library, follow these steps:

1. Open your Android project in Android Studio.
2. Add the following lines to settings.gradle:

{% tabs %}
{% tab title="Groovy" %}
```kotlin
allprojects {
	repositories {
		maven { url 'https://jitpack.io' }
	}
}
	
```
{% endtab %}

{% tab title="Kts" %}
```kotlin
repositories {
        maven ("https://jitpack.io")
}
```
{% endtab %}
{% endtabs %}

3. Add the following lines to your app-level `build.gradle` file:

{% tabs %}
{% tab title="Groovy" %}
```kotlin
dependencies {
    implementation 'com.github.monafarmani:new:0.0.12'
}
```
{% endtab %}

{% tab title="Kts" %}
```kotlin
dependencies {
    implementation ("com.github.monafarmani:new:0.0.12")
}
```
{% endtab %}
{% endtabs %}



4. We need to implement settings for map box because it is used in our library, so add the following lines to settings.gradle too:

{% tabs %}
{% tab title="Groovy" %}
```kotlin
allprojects {
    repositories {
      maven {
            url 'https://api.mapbox.com/downloads/v2/releases/maven'
            authentication {
                basic(BasicAuthentication)
            }
            credentials {
                username = "mapbox"
                password = "MAPBOX_SECRET_KEY"
            }
        }
    }
}
```
{% endtab %}

{% tab title="Kts" %}
```kotlin
repositories {
    maven {
        url = uri("https://api.mapbox.com/downloads/v2/releases/maven")
        authentication {
            create<BasicAuthentication>("basic")
        }
        credentials {
            username = "mapbox"
            password = "MAPBOX_SECRET_KEY"
        }
    }
}
```
{% endtab %}
{% endtabs %}



5. Sync your project with Gradle.

