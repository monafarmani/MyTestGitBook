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

The provided endpoint response contains an array of agreements properties' list, including &#x20;

**question:** the question property represents a string or text that represents a question being posed, e.g.&#x20;

**answer:** the answer property represents a string or text that provides the corresponding answer to the question, e.g.&#x20;



### <mark style="color:green;">Config</mark>

The endpoint is designed to handle requests for retrieving or fetching configuration settings or information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Config" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of config properties, including &#x20;

**aspectRatio:** the aspectRatio property represents a string value that describes the aspect ratio of a visual element. Aspect ratio is the proportional relationship between the width and height of an object or display. The specific value of "string" is a placeholder, and in practice, it would typically provide a specific aspect ratio value such as **"16:9"** or **"4:3"**.

**chunkSize:** the chunkSize property represents a numerical value that indicates the size or length of chunks or segments, e.g.  . The unit of measurement for this value is  .

**lastGpsRecords:** the lastGpsRecords property represents a numerical value that indicates the number of recent GPS records or data points. It suggests how many GPS records are included or considered in the response, e.g.&#x20;

**toleranceInXAxis, toleranceInYAxis, toleranceInZAxis:** these properties represent numerical values that indicate tolerances or acceptable ranges along the X, Y, and Z axes, respectively, e.g. . The unit of measurement for these tolerance values are&#x20;

### <mark style="color:green;">Geo Code</mark>

The endpoint is designed to handle requests for geocoding addresses or place names.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Map/geoCode" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**OriginLatitude :**

**OriginLongitude :**

**DestinationLatitude :**

**DestinationLongitude :**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of Geo Code properties, including&#x20;

**origin:** The origin property represents a string value that describes the origin location, e.g.&#x20;

**originPlace:** The originPlace property represents a string value that provides additional information about the origin. It could refer to the name, address, or any other relevant details related to the origin location or place, e.g.

**destination:** The destination property represents a string value that describes the destination location, e.g.&#x20;

**destinationPlace:** The destinationPlace property represents a string value that provides additional information about the destination. It could refer to the name, address, or any other relevant details related to the destination location or place, e.g.



### <mark style="color:green;">**Privacy Policy**</mark>

The endpoint is designed to handle requests for retrieving or fetching a privacy policy from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/PrivacyPolicy" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of privacy policy properties, including&#x20;

**lastUpdate :** the lastUpdate property represents a specific date and time when the information or data was last updated, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.

**privacyPolicies :** the privacyPolicies property represents an array of objects that contain information about privacy policies. In this case, there is a single object within the array.

Within the privacyPolicies object:

**id :** the id property represents a numerical identifier associated with a privacy policy entry, e.g.

**question :** the question property represents a string or text that serves as a question related to privacy policies, e.g.

**answer :** the answer property represents a string or text that provides the corresponding answer to the privacy policy question, e.g.

**order :** the order property represents a numerical value indicating the order or sequence of the privacy policy entry, e.g.

**createDate :** the createDate property represents a specific date and time when the privacy policy entry was created, e.g.

**modifyDate :** the modifyDate property represents a specific date and time when the privacy policy entry was last modified, e.g.



### <mark style="color:green;">Terms & Conditions</mark>

The endpoint is designed to handle requests for retrieving or fetching terms and conditions information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/terms" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of terms & conditions properties' list, including&#x20;

**question :** The question property represents a string or text that serves as a questionof terms & conditions, e.g.&#x20;

**answer :** The answer property represents a string or text that provides the corresponding answer to the question, e.g.&#x20;
