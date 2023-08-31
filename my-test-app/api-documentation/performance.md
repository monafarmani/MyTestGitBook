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

# Performance

### <mark style="color:green;">**Report**</mark>&#x20;

The endpoint is designed to handle requests for generating a report of trips or journeys. It allows users to retrieve aggregated or summarized information about multiple trips based on certain criteria or filters.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/report" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**UserTripReportType:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of report properties, including:&#x20;

**date:** the date property represents a specific date and time, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.

**score:** the score property represents a numerical score associated with a particular event or data, e.g. **20**.

**label:** the label property represents a string or text label associated with the event or data. It is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.



### <mark style="color:green;">**Driving Score**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the driving score information associated with a trip or journey. It allows users to access details about the driving performance or behavior during a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/drivingScore" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of report property, which is:&#x20;

**averageScore:** the averageScore property represents the average score associated with a specific context or set of data. It is expected to be a numeric value, e.g. **50**.



### <mark style="color:green;">**Event Stats**</mark>&#x20;

The endpoint is designed to handle requests for retrieving event statistics within a trip report. It allows users to access aggregated information and statistics related to specific events or incidents that occurred during trips or journeys.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/report/eventStats" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**TripReportType:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of a list of event stats properties, including:&#x20;

**title:** the title property represents a string or text that serves as a title or heading. It typically describes or identifies a specific item or category, e.g.&#x20;

**subtitle:** the subtitle property represents a string or text that serves as a subtitle or secondary information related to the title. It provides additional details or context about the item or category, e.g.&#x20;

**score :** the score property represents a numerical score associated with the item or category being described. The value 0 indicates the score achieved for that specific item or category.

**difference:** the difference property represents a numerical value indicating the difference or change related to the score. It provides information about how the score has changed compared to a previous value or reference
