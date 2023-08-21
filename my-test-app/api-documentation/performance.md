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

**UserTripReportType :**

#### <mark style="color:orange;">**Response**</mark>

**date :** The date property represents a specific date and time. The value of "2023-08-15T11:12:36.801Z" indicates a timestamp in UTC format, representing the date and time when the associated event or data was recorded.

**score :** The score property represents a numerical score associated with a particular event or data. The value 0 indicates the score achieved for the event or data.

**label :** The label property represents a string or text label associated with the event or data. The value "string" is a placeholder, and in practice, it would typically provide a descriptive label or category related to the event or data.



### <mark style="color:green;">**Driving Score**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the driving score information associated with a trip or journey. It allows users to access details about the driving performance or behavior during a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/drivingScore" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

**averageScore :** The averageScore property represents the average score associated with a specific context or set of data. In this case, the value is 0, which suggests that the average score is zero.



### <mark style="color:green;">**Event Stats**</mark>&#x20;

The endpoint is designed to handle requests for retrieving event statistics within a trip report. It allows users to access aggregated information and statistics related to specific events or incidents that occurred during trips or journeys.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/report/eventStats" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**TripReportType :**

#### <mark style="color:orange;">**Response**</mark>

**title :** The title property represents a string or text that serves as a title or heading. It typically describes or identifies a specific item or category.

**subtitle :** The subtitle property represents a string or text that serves as a subtitle or secondary information related to the title. It provides additional details or context about the item or category.

**score :** The score property represents a numerical score associated with the item or category being described. The value 0 indicates the score achieved for that specific item or category.

**difference :** The difference property represents a numerical value indicating the difference or change related to the score. It provides information about how the score has changed compared to a previous value or reference
