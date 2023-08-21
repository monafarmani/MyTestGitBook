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

# Trip

### <mark style="color:green;">**Create Trip**</mark>&#x20;

The endpoint is designed to handle requests for creating a new trip or journey within the system. It allows users to submit the necessary information and parameters to define and initiate a new trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/createTrip" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Upoload Start</mark>

The endpoint is designed to handle requests for initiating the start of a file upload process related to a trip. It allows users to begin uploading a file or multiple files associated with the trip to the server.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadStart" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Upload Chunks</mark>

The endpoint is designed to handle requests for uploading file chunks of a trip to the server. When a large file needs to be uploaded, it is often split into smaller chunks for efficient and reliable transmission.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadChunks" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Complete Chunks</mark>

The endpoint is designed to handle requests for indicating the completion of a file upload process related to a trip. It allows users to signal that all file chunks associated with the trip have been successfully uploaded.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadComplete" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get File Chunk Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the status of file chunks related to a trip. It allows users to check the status of individual or multiple file chunks that make up a larger file associated with the trip.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/fileChunkStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get Files Of Completed Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the completion status of files related to a trip. It allows users to check whether the files associated with the trip have been completed or not.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/filesCompletedStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

### <mark style="color:green;">**Get List Of Trips**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Query Parameters</mark>

**keyword :**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response is a JSON array containing a single object. Here's the breakdown of each property within the object and their potential meanings:

**id :** This property likely represents the ID of the object or item. It is expected to be a numeric value (`0` in this case).

**score :** The `score` property likely represents a score or rating associated with the object. It is expected to be a numeric value (`0` in this case).

**isCompleted :** The `isCompleted` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the object or associated task is completed.

**createDate :** This property represents the date and time when the object or item was created. In the provided response, it is formatted as "2023-08-15T11:12:36.799Z", indicating the date and time in ISO 8601 format with UTC (Coordinated Universal Time).

**originAddress :** The `originAddress` property likely represents the address of the origin location. It is expected to be a string value.

**originPostalCode :** This property represents the postal code associated with the origin location. It is expected to be a string value.

**originLocality :** The `originLocality` property represents the locality or city of the origin location. It is expected to be a string value.

**originplace :** This property likely represents the name or identifier of the origin place. It is expected to be a string value.

**originRegion :** The `originRegion` property represents the region or state of the origin location. It is expected to be a string value.

**destinationaddress :** The `destinationAddress` property represents the address of the destination location. It is expected to be a string value.

**destinationPostalCode :** This property represents the postal code associated with the destination location. It is expected to be a string value.

**destinationLocality :** The `destinationLocality` property represents the locality or city of the destination location. It is expected to be a string value.

**destinationPlace :** This property likely represents the name or identifier of the destination place. It is expected to be a string value.

**destinationRegion :** The `destinationRegion` property represents the region or state of the destination location. It is expected to be a string value.

**startdatetime :** The `startDateTime` property represents the date and time when the object or item's activity or event starts. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**endDateTime:** This property represents the date and time when the object or item's activity or event ends. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**duration:** The `duration` property is an object that contains sub-properties representing the duration of the object or item. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).



### <mark style="color:green;">**Get Trip By Id**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Path Parameters</mark>

**id :**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON object containing properties related to an event or task. Here's the breakdown of each property and its potential meaning:

**`id`:** This property likely represents the ID of the event or task. It is expected to be a numeric value (`0` in this case).

**`score`:** The `score` property likely represents a score or rating associated with the event or task. It is expected to be a numeric value (`0` in this case).

**`isCompleted`:** The `isCompleted` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the event or task is completed.

**`originAddress`:** The `originAddress` property represents the address of the origin location. It is expected to be a string value.

**`originPostalCode`:** This property represents the postal code associated with the origin location. It is expected to be a string value.

**`originLocality`:** The `originLocality` property represents the locality or city of the origin location. It is expected to be a string value.

**`originPlace`:** This property likely represents the name or identifier of the origin place. It is expected to be a string value.

**`originRegion`:** The `originRegion` property represents the region or state of the origin location. It is expected to be a string value.

**`origin`:** The `origin` property represents the overall origin information. It is expected to be a string value.

**`destinationAddress`:** The `destinationAddress` property represents the address of the destination location. It is expected to be a string value.

**`destinationPostalCode`:** This property represents the postal code associated with the destination location. It is expected to be a string value.

**`destinationLocality`:** The `destinationLocality` property represents the locality or city of the destination location. It is expected to be a string value.

**`destinationPlace`:** This property likely represents the name or identifier of the destination place. It is expected to be a string value.

**`destinationRegion`:** The `destinationRegion` property represents the region or state of the destination location. It is expected to be a string value.

**`destination`:** The `destination` property represents the overall destination information. It is expected to be a string value.

**`startDateTime`:** The `startDateTime` property represents the date and time when the event or task starts. It is formatted as "2023-08-15T11:12:36.800Z" in ISO 8601 format with UTC (Coordinated Universal Time).

**`endDateTime`:** This property represents the date and time when the event or task ends. It is formatted as "2023-08-15T11:12:36.800Z" in ISO 8601 format with UTC.

**`duration`:** The `duration` property is an object that contains sub-properties representing the duration of the event or task. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).

**`createDate`:** This property represents the date and time when the event or task was created. It is formatted as "2023-08-15T11:12:36.800Z", indicating the date and time in ISO 8601 format with UTC.



### <mark style="color:green;">**Get Last Trip**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the information of the last or most recent trip recorded in the system. It allows users to access details about the latest trip they have taken or the most recently recorded trip in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/last" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON object containing properties related to an event or task, including GPS information. Here's the breakdown of each property and its potential meaning:

**`id`:** This property likely represents the ID of the event or task. It is expected to be a numeric value (`0` in this case).

**`createDate`:** This property represents the date and time when the event or task was created. It is formatted as "2023-08-15T11:12:36.801Z", indicating the date and time in ISO 8601 format with UTC (Coordinated Universal Time).

**`startDateTime`:** The `startDateTime` property represents the date and time when the event or task starts. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**`endDateTime`:** This property represents the date and time when the event or task ends. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**`duration`:** The `duration` property is an object that contains sub-properties representing the duration of the event or task. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).

**`origin`:** The `origin` property represents the overall origin information. It is expected to be a string value.

**`destination`:** The `destination` property represents the overall destination information. It is expected to be a string value.

**`originPlace`:** This property likely represents the name or identifier of the origin place. It is expected to be a string value.

**`destinationPlace`:** This property likely represents the name or identifier of the destination place. It is expected to be a string value.

**`score`:** The `score` property likely represents a score or rating associated with the event or task. It is expected to be a numeric value (`0` in this case).

**`gpsInfo`:** The `gpsInfo` property is an array containing GPS information. In the provided response, it contains a single object with the following GPS-related properties:

**`gpsTime`:** The `gpsTime` property represents the date and time of the GPS information. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**`altitude`:** The `altitude` property represents the altitude value. It is expected to be a numeric value (`0` in this case).

**`latitude`:** The `latitude` property represents the latitude coordinate. It is expected to be a numeric value (`0` in this case).

**`longitude`:** The `longitude` property represents the longitude coordinate. It is expected to be a numeric value (`0` in this case).

**`speed`:** The `speed` property represents the speed value. It is expected to be a string value.

**`climb`:** The `climb` property represents the climb value. It is expected to be a string value.

**`course`:** The `course` property represents the course value. It is expected to be a string value.

**`epx`:** The `epx` property represents the estimated position error along the X-axis. It is expected to be a string value.

**`epy`:** The `epy` property represents the estimated position error along the Y-axis. It is expected to be a string value.

**`epv`:** The `epv` property represents the estimated position error vertically. It is expected to be a string value.

**`eps`:** The `eps` property represents the estimated speed error. It is expected to be a string value.

**`epc`:** The `epc` property represents the estimated climb error. It is expected to be a string value.

**`epd`:** The `epd` property represents the estimated course error. It is expected to be a string value.



### <mark style="color:green;">Get Total Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the total carbon emissions or carbon footprint of a trip or journey. It allows users to access information about the environmental impact in terms of carbon emissions resulting from a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/totalCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get Last Trip's Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the carbon emissions or carbon footprint of the last or most recent trip recorded in the system. It allows users to access information about the environmental impact in terms of carbon emissions resulting from the most recent trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/lastTripCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get Trip GPS By Id</mark>

The endpoint is designed to handle requests for retrieving or fetching GPS data associated with a specific trip. It allows users to access the latitude and longitude coordinates or other relevant GPS information recorded during the trip.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/Trip/{id}/gps" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get Trip Event Stats By Id</mark>

The endpoint is designed to handle requests for retrieving or fetching event statistics related to a specific trip. It allows users to access aggregated data or metrics about various events that occurred during the trip.

{% swagger src="../../.gitbook/assets/swagger (3).json" path="/api/v4/Trip/{id}/eventStats" method="get" expanded="true" %}
[swagger (3).json](<../../.gitbook/assets/swagger (3).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>
