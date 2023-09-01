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

# Settings

### <mark style="color:green;">Agreements</mark>

The endpoint is designed to handle requests for retrieving or fetching agreements. It allows users to access information about agreements stored in the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/agreements" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of several properties, including&#x20;

**question:** the question property represents a string or text that represents a question of the app's agreement being posed, e.g. **"APPLICABLE LAW"**.

**answer:** the answer property represents a string or text that provides the corresponding answer to the question, e.g. **"This License Agreement is governed by the German Basic Law excluding its conflicts of law rules."**.



### <mark style="color:green;">**Privacy Policy**</mark>

The endpoint is designed to handle requests for retrieving or fetching a privacy policy from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/PrivacyPolicy" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties, including&#x20;

**lastUpdate :** the lastUpdate property represents a specific date and time when the information or data was last updated, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-03-13T12:15:11.6972145"**.

**privacyPolicies :** the privacyPolicies property represents an array of objects that contain information about privacy policies, including

* **id :** the id property represents a numerical identifier associated with a privacy policy entry, e.g. **36**.
* **question :** the question property represents a string or text that serves as a question related to privacy policies, e.g. **"Changes to Privacy Policy"**.
* **answer :** the answer property represents a string or text that provides the corresponding answer to the privacy policy question, e.g. **"We may revise this Privacy Policy from time to time in our sole discretion. If there are any material changes to this Privacy Policy, we will notify you as required by applicable law. You understand and agree that you will be deemed to have accepted the updated Privacy Policy if you continue to use the App after the new Privacy Policy takes effect."**.
* **order :** the order property represents a numerical value indicating the order or sequence of the privacy policy entry, e.g. **7**.
* **createDate :** the createDate property represents a specific date and time when the privacy policy entry was created, e.g. **"2023-03-13T12:21:28.239462"**.
* **modifyDate :** the modifyDate property represents a specific date and time when the privacy policy entry was last modified, e.g. **null**.
* **getMaxDate:** the getMaxDate property represents the maximum date and time for the privacy policy, e.g. **"2023-03-13T12:21:28.239462"**.



### <mark style="color:green;">Terms & Conditions</mark>

The endpoint is designed to handle requests for retrieving or fetching terms and conditions information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/terms" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of several properties, including&#x20;

**question:** The question property represents a string or text that serves as a question of terms & conditions, e.g. **"Payment"**.

**answer:** The answer property represents a string or text that provides the corresponding answer to the question, e.g. **"The App is provided to you free of charge and you will not be charged for installing the App.\r\nGIZO charges insurance companies service fees for providing safety functions, driving data collection and analysis services."**.



### <mark style="color:green;">Config</mark>

The endpoint is designed to handle requests for retrieving or fetching configuration settings or information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Config" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties, including &#x20;

**aspectRatio:** the aspectRatio property represents a string value that describes the aspect ratio of a visual element, e.g. **"16:9"** or **"4:3"**. Aspect ratio is the proportional relationship between the width and height of an object or display.  .

**chunkSize:** the chunkSize property represents a numerical value that indicates the size or length of chunks or segments, e.g. **10485760**. The unit of measurement for this value is byte.

**lastGpsRecords:** the lastGpsRecords property represents a numerical value that indicates the number of recent GPS records or data points. It suggests how many GPS records are included or considered in the response, e.g. **100**.

**toleranceInXAxis, toleranceInYAxis, toleranceInZAxis:** these properties represent numerical values that indicate tolerances or acceptable ranges along the X, Y, and Z axes, respectively, e.g. **01**, **0.05**, **0.1,** respectively.&#x20;



### <mark style="color:green;">Geo Code</mark>

The endpoint is designed to handle requests for geocoding addresses or place names.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Map/geoCode" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**OriginLatitude:** the latitude of the trip's origin location. It's expected to be a numeric value, e.g**. 50.767002**.

**OriginLongitude:** the longitude of the trip's origin location. It's expected to be a numeric value, e.g**. 6.1035986**.

**DestinationLatitude:** the latitude of the trip's destination location. It's expected to be a numeric value, e.g**. 50.782578**.

**DestinationLongitude:** the longitude of the trip's destination location. It's expected to be a numeric value, e.g**. 6.0769243**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties, including

**origin:** the origin property represents a string value that describes the origin address or location, e.g. **"Burtscheid, Aachen, North Rhine-Westphalia"**.&#x20;

**originPlace:** the originPlace property represents a string value that provides additional information about the origin, e.g. **"Aachen"**.

**destination:** the destination property represents a string value that describes the destination address or location, e.g. **"Ponttor, Aachen, North Rhine-Westphalia"**. &#x20;

**destinationPlace:** the destinationPlace property represents a string value that provides additional information about the destination, e.g. **"Aachen"**.
