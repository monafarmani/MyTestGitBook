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

#### <mark style="color:orange;">Request Query Parameters</mark>

**UserTripReportType:** it specifies the type of report scores, and is expected to be a numeric value, e.g. **1**.

<mark style="color:red;">**Note:**</mark>** ** the report type of DAILY will return **1**, WEEKLY will return **2**, MONTHLY will return **3**, and YEARLY will return **5**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of several properties, including

**date:** the date property represents a specific date and time of the report, which is formatted as "yyyy-MM-dd'T'HH:mm:ss", and it is expected to be a string value, e.g. **"2023-08-29T00:00:00+00:00"**.

**score:** the score property represents a numerical score associated with the scores of all of the user's trips during the specific time, e.g. **91.5**.

**label:** the label property represents a string or text label associated with the trip. It is expected to be a string value, e.g. **"Tue"**.

<mark style="color:red;">**Note:**</mark> the label is determined based on the type of report. If the report type is DAILY, the label is the days of the week. For WEEKLY, it's the weeks of the month. For MONTHLY, it's the months of the year, and for YEARLY, it's the number of the year. &#x20;



### <mark style="color:green;">**Driving Score**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the driving score information associated with a trip or journey. It allows users to access details about the driving performance or behavior during a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/drivingScore" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property, which is

**averageScore:** the averageScore property represents the average score gained from the total trips of the user. It is expected to be a numeric value, e.g. **95**.



### <mark style="color:green;">**Event Stats**</mark>&#x20;

The endpoint is designed to handle requests for retrieving event statistics within a trip report. It allows users to access aggregated information and statistics related to specific events or incidents that occurred during trips or journeys.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/report/eventStats" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**TripReportType:** it specifies the type of report scores, and is expected to be a numeric value, e.g. **1**.

<mark style="color:red;">**Note:**</mark>** ** the report type of DAILY will return **1**, WEEKLY will return **2**, MONTHLY will return **3**, and YEARLY will return **5**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of several properties, including

**title:** the title property represents a string or text that serves as a title or heading. It typically describes or identifies an event's stats.

**subtitle:** the subtitle property represents a string or text that serves as a subtitle or secondary information related to the title. It provides additional details or context about the item or category.&#x20;

**score :** the score property represents a numerical score associated with the item or category being described, e.g. **20**.

**difference:** the difference property represents a numerical value indicating the difference or change related to the score. It provides information about how the score has changed compared to a previous value or reference, e.g. **20**.
