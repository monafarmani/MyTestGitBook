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

The endpoint is designed to handle requests for creating a new trip or journey within the system.&#x20;

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/createTrip" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property which is : &#x20;

**tripId:** the tripId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.



### <mark style="color:green;">Upload Start</mark>

The endpoint is designed to handle requests for initiating the start of a file upload process related to a trip. It allows users to begin uploading a file or multiple files associated with the trip to the server.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadStart" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**ItemId:** the itemId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**chunkCount:** the chunk count represents the total number of the smaller chunks that make up the entire file, and it is expected to be an Integer value, e.g. **10**.

**FileType:** It specifies the type of uploading file, and it is expected to be an Integer value.&#x20;

For example, VIDEO.type will return **0**, IMU.type will return **1**, GPS.type will return **2**, TTC.type will return **4**, and MATRIX.type will return **5**.

**FileExtension:** It specifies the type of file extension, and it is expected to be an Integer value.&#x20;

For example, FileExtension.VIDEO\_MP4 will return **1**, FileExtension.TEXT\_CSV will return **3**, and FileExtension.TEXT\_TXT will return **4**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property which is :&#x20;

**fileManagerId:** the fileManagerId property represents an identifier or reference to a file manager which is going to be used in [Upload Chunks](trip.md#upload-chunks). It is expected to be a numeric value, e.g. **1002**.



### <mark style="color:green;">Upload Chunks</mark>

The endpoint is designed to handle requests for uploading file chunks of a trip to the server. When a large file needs to be uploaded, it is often split into smaller chunks for efficient and reliable transmission.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadChunks" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

These parameters should be sent in multipart/form-data format

**FileId:** the fileId property represents an identifier or reference to a file manager. It is expected to be a numeric value, e.g. **1002**.

**FileChunkId:** this property represents the identifier of a file chunk's. It is expected to be a numeric value, e.g. **2**

&#x20;**FileType:** It specifies the type of uploading file, and it is expected to be an Integer value.&#x20;

For example, VIDEO.type will return **0**, IMU.type will return **1**, GPS.type will return **2**, TTC.type will return **4**, and MATRIX.type will return **5**.

**FileChunk:** this property represents the content of a file chunk, and It is expected to be a file value.

<mark style="color:red;">**Note:**</mark> the type content for HttpHeaders can be either ContntType.VIDEO\_MP4 or ContntType.TEXT\_CSV.&#x20;



#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**id:** the id property represents an identifier or reference associated with the process. In this case, the value is 0, indicating that either an ID has not been assigned yet or the process has not been initiated.

**mergeStatus:** the mergeStatus property indicates the status of a merge operation. When set to true, it suggests that the merge process has been successfully completed.

**uploadPercent:** the uploadPercent property represents the progress or percentage of an upload process. The value of 0 indicates that the upload process has not yet started or is in its initial stage.



### <mark style="color:green;">Complete Chunks</mark>

The endpoint is designed to handle requests for indicating the completion of a file upload process related to a trip. It allows users to signal that all file chunks associated with the trip have been successfully uploaded.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadComplete" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**ItemId:**

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">Get File Chunk Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the status of file chunks related to a trip. It allows users to check the status of individual or multiple file chunks that make up a larger file associated with the trip.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/fileChunkStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**TripId:**

**TripFileType:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**fileChunkIds:** the fileChunkIds property is an array that contains the identifiers or references for the file chunks associated with the upload process. In this case, there is one element in the array with a value of 0, indicating that there is one file chunk associated with the upload.

**chunkSize:** the chunkSize property represents the size of each file chunk in bytes. The value of 0 in this case suggests that either the chunk size has not been determined or is not applicable for the specific upload process.

**fileId:** the fileId property is the identifier or reference for the uploaded file. The value of 0 indicates that either an ID has not been assigned yet or the file has not been uploaded.

**isUploaded:** the isUploaded property is a boolean value that indicates whether the file has been successfully uploaded. In this case, the value is true, suggesting that the upload process has been completed successfully.

**uploadPercent:** the uploadPercent property represents the progress or percentage of the upload process. The value of 0 indicates that the upload process has not yet started or is in its initial stage.

### <mark style="color:green;">Get Files Of Completed Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the completion status of files related to a trip. It allows users to check whether the files associated with the trip have been completed or not.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/filesCompletedStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**tripId:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**isCompleted:** the isCompleted property is a boolean value that indicates whether the process or operation has been completed. In this case, the value is true, suggesting that the process has been successfully completed.

**message:** the message property provides a string value that typically includes additional information or a status message related to the completion of the process. The actual value of the string would depend on the specific implementation or context of the endpoint. It may contain details about the completed process, any relevant information or instructions, or an indication of success or failure.



### <mark style="color:green;">**Get List Of Trips**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**keyword:**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**id:** this property likely represents the ID of the object or item. It is expected to be a numeric value (`0` in this case).

**score:** the `score` property likely represents a score or rating associated with the object. It is expected to be a numeric value (`0` in this case).

**isCompleted:** the `isCompleted` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the object or associated task is completed.

**createDate:** this property represents the date and time when the object or item was created. In the provided response, it is formatted as "2023-08-15T11:12:36.799Z", indicating the date and time in ISO 8601 format with UTC (Coordinated Universal Time).

**originAddress:** the `originAddress` property likely represents the address of the origin location. It is expected to be a string value.

**originPostalCode:** this property represents the postal code associated with the origin location. It is expected to be a string value.

**originLocality:** the `originLocality` property represents the locality or city of the origin location. It is expected to be a string value.

**originplace:** this property likely represents the name or identifier of the origin place. It is expected to be a string value.

**originRegion:** the `originRegion` property represents the region or state of the origin location. It is expected to be a string value.

**destinationaddress:** the `destinationAddress` property represents the address of the destination location. It is expected to be a string value.

**destinationPostalCode:** this property represents the postal code associated with the destination location. It is expected to be a string value.

**destinationLocality:** the `destinationLocality` property represents the locality or city of the destination location. It is expected to be a string value.

**destinationPlace:** this property likely represents the name or identifier of the destination place. It is expected to be a string value.

**destinationRegion:** the `destinationRegion` property represents the region or state of the destination location. It is expected to be a string value.

**startdatetime:** the `startDateTime` property represents the date and time when the object or item's activity or event starts. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**endDateTime:** this property represents the date and time when the object or item's activity or event ends. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**duration:** the `duration` property is an object that contains sub-properties representing the duration of the object or item. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).



### <mark style="color:green;">**Get Trip By Id**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Path Parameters</mark>

**id:**&#x20;

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:green;">**Get Last Trip**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the information of the last or most recent trip recorded in the system. It allows users to access details about the latest trip they have taken or the most recently recorded trip in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/last" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**id:** this property likely represents the ID of the event or task. It is expected to be a numeric value (`0` in this case).

**craeteDate:** this property represents the date and time when the event or task was created. It is formatted as "2023-08-15T11:12:36.801Z", indicating the date and time in ISO 8601 format with UTC (Coordinated Universal Time).

**startDateTime:** the `startDateTime` property represents the date and time when the event or task starts. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**endDateTime:** this property represents the date and time when the event or task ends. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**duration:**  the `duration` property is an object that contains sub-properties representing the duration of the event or task. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).

**origin:** the `origin` property represents the overall origin information. It is expected to be a string value.

**destination:** the `destination` property represents the overall destination information. It is expected to be a string value.

**originPlace:** this property likely represents the name or identifier of the origin place. It is expected to be a string value.

**destinationPlace:** this property likely represents the name or identifier of the destination place. It is expected to be a string value.

**score:** the `score` property likely represents a score or rating associated with the event or task. It is expected to be a numeric value (`0` in this case).

**gpsInfo:** the `gpsInfo` property is an array containing GPS information. In the provided response, it contains a single object with the following GPS-related properties:

**gpsTime:** the `gpsTime` property represents the date and time of the GPS information. It is formatted as "2023-08-15T11:12:36.801Z" in ISO 8601 format with UTC.

**altitude:** the `altitude` property represents the altitude value. It is expected to be a numeric value (`0` in this case).

**latitude:** the `latitude` property represents the latitude coordinate. It is expected to be a numeric value (`0` in this case).

**longitude:** the `longitude` property represents the longitude coordinate. It is expected to be a numeric value (`0` in this case).

**speed:** the `speed` property represents the speed value. It is expected to be a string value.

**climb:**  the `climb` property represents the climb value. It is expected to be a string value.

**course:** the `course` property represents the course value. It is expected to be a string value.

**epx:** the `epx` property represents the estimated position error along the X-axis. It is expected to be a string value.

**epy:** the `epy` property represents the estimated position error along the Y-axis. It is expected to be a string value.

**epv:** the `epv` property represents the estimated position error vertically. It is expected to be a string value.

**eps:** the `eps` property represents the estimated speed error. It is expected to be a string value.

**epc:** the `epc` property represents the estimated climb error. It is expected to be a string value.

**epd:** the `epd` property represents the estimated course error. It is expected to be a string value.



### <mark style="color:green;">Get Total Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the total carbon emissions or carbon footprint of a trip or journey. It allows users to access information about the environmental impact in terms of carbon emissions resulting from a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/totalCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**carbon:** the carbon property represents the amount of carbon emissions associated with a particular process, activity, or calculation. In this case, the value is 0, which suggests that there are no carbon emissions associated with the specific context being referred to.



### <mark style="color:green;">Get Last Trip's Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the carbon emissions or carbon footprint of the last or most recent trip recorded in the system. It allows users to access information about the environmental impact in terms of carbon emissions resulting from the most recent trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/lastTripCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**carbon:** the carbon property represents the amount of carbon emissions associated with a particular process, activity, or calculation. In this case, the value is 0, which suggests that there are no carbon emissions associated with the specific context being referred to.

**lastUpdate:** the lastUpdate property indicates the date and time when the carbon emission information was last updated. The value of "2023-08-15T11:12:36.801Z" represents the specific timestamp in UTC format.



### <mark style="color:green;">Get Trip GPS By Id</mark>

The endpoint is designed to handle requests for retrieving or fetching GPS data associated with a specific trip. It allows users to access the latitude and longitude coordinates or other relevant GPS information recorded during the trip.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/Trip/{id}/gps" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**gpsDetail:** the gpsDetail property is an array that contains objects representing GPS information. Each object within the array includes properties such as gpsTime, latitude, and longitude. These properties provide details about the GPS coordinates and the timestamp when the GPS information was recorded.

**events:** the events property is an array that contains objects representing events associated with the GPS data. Each object within the array includes properties such as eventType, latitude, and longitude. These properties provide details about the event type and its associated GPS coordinates



### <mark style="color:green;">Get Trip Event Stats By Id</mark>

The endpoint is designed to handle requests for retrieving or fetching event statistics related to a specific trip. It allows users to access aggregated data or metrics about various events that occurred during the trip.

{% swagger src="../../.gitbook/assets/swagger (3).json" path="/api/v4/Trip/{id}/eventStats" method="get" expanded="true" %}
[swagger (3).json](<../../.gitbook/assets/swagger (3).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**eventType:** the eventType property represents the type of event that occurred. The value 0 suggests that it is a specific type of event, and the exact meaning of this event would depend on the application or system's context.

**score:** the score property represents a score associated with the event. The value 0 indicates the score achieved for the event.

**scorePercentile:** the scorePercentile property represents the percentile rank of the score achieved for the event. The value 0 suggests that the score percentile is at the lowest rank.

**events:** the events property is an array that contains objects representing specific events. Each event object includes properties such as time, value, latitude, longitude, and location. These properties provide details about the event's time, value, GPS coordinates, and location.

**eventDetected:** the eventDetected property is an array that contains objects representing detected events. Each detected event object includes properties such as time, latitude, longitude, speedLimit, and yourSpeed. These properties provide details about the detected event's time, GPS coordinates, speed limit, and actual speed.

**eventDetectedTailGating:** the eventDetectedTailGating property is an array that contains objects representing detected tailgating events. Each detected tailgating event object includes properties such as time, speedInKmph, ttc, and depth. These properties provide details about the detected tailgating event's time, speed in kilometers per hour, time-to-collision (TTC), and depth.

**rideTimeEvent:** the rideTimeEvent property represents information related to ride time. It includes sub-properties such as totalTime and tripDistance. The totalTime property further includes sub-properties like hours, minutes, and seconds, representing the total time of the ride in hours, minutes, and seconds. The tripDistance property represents the distance covered during the ride.

