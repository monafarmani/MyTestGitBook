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



**question :** The question property represents a string or text that represents a question being posed.

**answer :** The answer property represents a string or text that provides the corresponding answer to the question.&#x20;



### <mark style="color:green;">Config</mark>

The endpoint is designed to handle requests for retrieving or fetching configuration settings or information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Config" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>



**aspectRatio :** The aspectRatio property represents a string value that describes the aspect ratio of a visual element. Aspect ratio is the proportional relationship between the width and height of an object or display. The specific value of "string" is a placeholder, and in practice, it would typically provide a specific aspect ratio value such as "16:9" or "4:3".

**chunkSize :** The chunkSize property represents a numerical value that indicates the size or length of chunks or segments. The unit of measurement for this value would depend on the specific context and application.

**lastGpsRecords :** The lastGpsRecords property represents a numerical value that indicates the number of recent GPS records or data points. It suggests how many GPS records are included or considered in the response.

**toleranceInXAxis, toleranceInYAxis, toleranceInZAxis :** These properties represent numerical values that indicate tolerances or acceptable ranges along the X, Y, and Z axes, respectively. The specific context or application will determine the meaning and unit of measurement for these tolerance values.

### <mark style="color:green;">Geo Code</mark>

The endpoint is designed to handle requests for geocoding addresses or place names.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Map/geoCode" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



**origin :** The origin property represents a string value that describes the origin of something. It could refer to the starting point or location of a journey, transportation route, or any other context where a point of origin is relevant. The specific value of "string" is a placeholder, and in practice, it would typically provide a specific origin description or identifier.

**originPlace :** The originPlace property represents a string value that provides additional information about the origin. It could refer to the name, address, or any other relevant details related to the origin location or place.

**destination :** The destination property represents a string value that describes the destination of something. It could refer to the endpoint or target location of a journey, transportation route, or any other context where a destination point is relevant. The specific value of "string" is a placeholder, and in practice, it would typically provide a specific destination description or identifier.

**destinationPlace :** The destinationPlace property represents a string value that provides additional information about the destination. It could refer to the name, address, or any other relevant details related to the destination location or place.



### <mark style="color:green;">**Privacy Policy**</mark>

The endpoint is designed to handle requests for retrieving or fetching a privacy policy from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/PrivacyPolicy" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>



**lastUpdate :** The lastUpdate property represents a specific date and time when the information or data was last updated. The value of "2023-08-15T11:12:36.799Z" indicates a timestamp in UTC format, representing the date and time of the last update.

**privacyPolicies :** The privacyPolicies property represents an array of objects that contain information about privacy policies. In this case, there is a single object within the array.

Within the privacyPolicies object:

**id :** The id property represents a numerical identifier associated with a privacy policy entry.

**question :** The question property represents a string or text that serves as a question related to privacy policies.

**answer :** The answer property represents a string or text that provides the corresponding answer to the privacy policy question.

**order :** The order property represents a numerical value indicating the order or sequence of the privacy policy entry.

**createDate :** The createDate property represents a specific date and time when the privacy policy entry was created.

**modifyDate :** The modifyDate property represents a specific date and time when the privacy policy entry was last modified.



### <mark style="color:green;">Terms & Conditions</mark>

The endpoint is designed to handle requests for retrieving or fetching terms and conditions information from the system or application.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/terms" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>



**question :** The question property represents a string or text that serves as a question. The value of "string" is a placeholder and would typically be replaced with an actual question.

**answer :** The answer property represents a string or text that provides the corresponding answer to the question. The value of "string" is a placeholder and would typically be replaced with an actual answer.&#x20;
