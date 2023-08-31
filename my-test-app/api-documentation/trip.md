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

The provided endpoint response contains a property which is: &#x20;

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

**chunkCount:** the chunk count represents the total number of the smaller chunks that make up the entire file, and it is expected to be a numeric value, e.g. **10**.

**FileType:** it specifies the type of uploading file, and it is expected to be an numeric value, e.g. **0**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO will return **0**, IMU will return **1**, GPS will return **2**, TTC will return **4**, and MATRIX will return **5**.

**FileExtension:** it specifies the type of file extension, and it is expected to be an numeric value, e.g. **1**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO\_MP4 will return **1**, TEXT\_CSV will return **3**, and TEXT\_TXT will return **4**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property which is:&#x20;

**fileManagerId:** the fileManagerId property represents an identifier or reference to a file manager that is going to be used in [Upload Chunks](trip.md#upload-chunks). It is expected to be a numeric value, e.g. **1002**.



### <mark style="color:green;">Upload Chunks</mark>

The endpoint is designed to handle requests for uploading file chunks of a trip to the server. When a large file needs to be uploaded, it is often split into smaller chunks for efficient and reliable transmission.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadChunks" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

These parameters should be sent in multi-part/form-data format.

**FileId:** the fileId property represents an identifier or reference to a file manager. It is expected to be a numeric value, e.g. **1002**.

**FileChunkId:** this property represents the identifier of a file chunk. It is expected to be a numeric value, e.g. **2**.

&#x20;**FileType:** it specifies the type of uploading file, and it is expected to be an numeric value, e.g. **0**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO will return **0**, IMU will return **1**, GPS will return **2**, TTC will return **4**, and MATRIX will return **5**.

**FileChunk:** this property represents the content of a file chunk, and it is expected to be a file value.

<mark style="color:red;">**Note:**</mark> the type content for HttpHeaders can be either ContntType.VIDEO\_MP4 or ContntType.TEXT\_CSV.&#x20;

<mark style="color:red;">**Note:**</mark> the value for HttpHeaders in ContentDisposition should be "filename="${fileName}"".

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of upload chunks properties, including:&#x20;

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**mergeStatus:** the mergeStatus property indicates the status of a merge operation, and it is expected to be a Boolean value. When set to **true**, it suggests that the merge process has been successfully completed.

**uploadPercent:** the uploadPercent property represents the progress or percentage of an upload process. It is expected to be a numeric value, e.g. **30**.



### <mark style="color:green;">Complete Chunks</mark>

The endpoint is designed to handle requests for indicating the completion of a file upload process related to a trip. It allows users to signal that all file chunks associated with the trip have been successfully uploaded.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadComplete" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**ItemId:** the ItemId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

#### <mark style="color:orange;">**Response**</mark>

When set to **true**, it suggests that the file upload process related to a trip has been successfully completed.



### <mark style="color:green;">Get List Of Trips</mark>

The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**keyword:** it's a query that is used to search data, and it is expected to be a string value.

<mark style="color:red;">**Note:**</mark> if the keyword is empty, it will return the whole related data.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of a list of trip properties, including :

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**score:** the score property likely represents a score gotten from a trip, between 0 to 100. It is expected to be a numeric value, e.g. **70**.

**isCompleted:** the isCompleted property is a Boolean value (true or false). This property typically indicates whether uploading files is completed or not, e.g. **true** means it's completed.

**createDate:** this property represents the date and time when a trip was created, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.

**originAddress:** the originAddress property likely represents the address of the origin location. It is expected to be a string value, e.g. **"Jülicher Straße"**.

**originPostalCode:** this property represents the postal code associated with the origin location. It is expected to be a string value, e.g. **"52070"**.

**originLocality:** the originLocality property represents the locality or city of the origin location. It is expected to be a string value, e.g. **"Kalkofen"**.

**originPlace:** this property likely represents the name or identifier of the origin place. It is expected to be a string value, e.g. **"Aachen"**.

**originRegion:** the originRegion property represents the region or state of the origin location. It is expected to be a string value, e.g. **"North Rhine-Westphalia"**.

**origin:** the origin property represents the origin location. It is expected to be a string value, e.g. **"North Rhine-Westphalia, Aachen, Kalkofen"**.

**destinationAddress:** the destinationaddress property represents the address of the destination location. It is expected to be a string value, e.g. **"Roermonder Straße"**.

**destinationPostalCode:** this property represents the postal code associated with the destination location. It is expected to be a string value, e.g. **"52072"**.

**destinationLocality:** the destinationLocality property represents the locality or city of the destination location. It is expected to be a string value, e.g. **"Ponttor"**.

**destinationPlace:** this property likely represents the name or identifier of the destination place. It is expected to be a string value, e.g. **"Aachen"**.

**destinationRegion:** the destinationRegion property represents the region or state of the destination location. It is expected to be a string value, e.g. **"North Rhine Westphalia"**.

**destination:** the destination property represents the destination location. It is expected to be a string value, e.g. **"North Rhine Westphalia, Aachen, Ponttor"**.

**startDatetime:** the startDatetime property represents the date and time when a trip starts. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and is expected to be a string value, e.g. **"2023-07-25T15:41:45.282"**.

**endDateTime:** this property represents the date and time when a trip ends. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and is expected to be a string value, e.g. **"2023-07-25T15:41:57.481"**.

**duration:** the duration property is an object that contains sub-properties representing the duration of the trip. These sub-properties include ticks, days, hours, milliseconds, minutes, and seconds. Each sub-property is expected to be a numeric value, e.g. **"00:00:12.1990000"**.



### <mark style="color:green;">**Get Trip By ID**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Path Parameters</mark>

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of trip properties, including :

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**score:** the score property likely represents a score gotten from a trip, between 0 to 100. It is expected to be a numeric value, e.g. **70**.

**isCompleted:** the isCompleted property is a Boolean value (true or false). This property typically indicates whether uploading files is completedor not, e.g. **true** means it's completed.

**originAddress:** the originAddress property likely represents the address of the origin location. It is expected to be a string value, e.g. **"Jülicher Straße"**.

**originPostalCode:** this property represents the postal code associated with the origin location. It is expected to be a string value, e.g. **"52070"**.

**originLocality:** the originLocality property represents the locality or city of the origin location. It is expected to be a string value, e.g. **"Kalkofen"**.

**originPlace:** this property likely represents the name or identifier of the origin place. It is expected to be a string value, e.g. **"Aachen"**.

**originRegion:** the originRegion property represents the region or state of the origin location. It is expected to be a string value, e.g. **"North Rhine-Westphalia"**.

**origin:** the origin property represents the origin location. It is expected to be a string value, e.g. **"North Rhine-Westphalia, Aachen, Kalkofen"**.

**destinationAddress:** the destinationAddress property represents the address of the destination location. It is expected to be a string value, e.g. **"Roermonder Straße"**.

**destinationPostalCode:** this property represents the postal code associated with the destination location. It is expected to be a string value, e.g. **"52072"**.

**destinationLocality:** the destinationLocality property represents the locality or city of the destination location. It is expected to be a string value, e.g. **"Ponttor"**.

**destinationPlace:** this property likely represents the name or identifier of the destination place. It is expected to be a string value, e.g. **"Aachen"**.

**destinationRegion:** the destinationRegion property represents the region or state of the destination location. It is expected to be a string value, e.g. **"North Rhine Westphalia"**.

**destination:** the destination property represents the destination location. It is expected to be a string value, e.g. **"North Rhine Westphalia, Aachen, Ponttor"**.

**startDatetime:** the startDatetime property represents the date and time when a trip starts. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T15:41:45.282"**.

**endDateTime:** this property represents the date and time when a trip ends. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T15:41:57.481"**.

**duration:** the duration property is an object that contains sub-properties representing the duration of the trip. These sub-properties include ticks, days, hours, milliseconds, minutes, and seconds. Each sub-property is expected to be a numeric value, e.g. **"00:00:12.1990000"**.

**createDate:** this property represents the date and time when a trip was created which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.

### &#x20;

### <mark style="color:green;">Get Trip GPS By Id</mark>

The endpoint is designed to handle requests for retrieving or fetching GPS data associated with a specific trip. It allows users to access the latitude and longitude coordinates or other relevant GPS information recorded during the trip.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/Trip/{id}/gps" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:** the Id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of GPS properties, including:

**gpsDetail:** the gpsDetail property is an array that contains objects representing GPS information. Each object within the array includes properties such as gpsTime, latitude, and longitude. These properties provide details about the GPS coordinates and the timestamp when the GPS information was recorded.

* **gpsTime:** this key-value pair indicates the GPS time , which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS".  It's expected to be a string value, e.g. **"2023-08-    29T21:06:47.002+00:00**".
* &#x20;**latitude:** this key-value pair represents the latitude coordinate as a numeric value, e.g. **50.78181**. &#x20;
* **longitude:** this key-value pair represents the longitude coordinate as a numeric value, e.g. **6.070963**.

**events:** the events property is an array that contains objects representing events associated with the GPS data. Each object within the array includes properties such as eventType, eventName,  latitude, and longitude. These properties provide details about the event type and its associated GPS coordinates.

* **eventType:** this key-value pair represents the type of event as a numeric value, e.g. **0.**\
  \
  <mark style="color:red;">**Note:**</mark> the value 0 suggests that it is a "Harsh Accel", 1 means "Harsh Brake", 2 means "Harsh Corner", 3 means "Speeding", 4 means "TailGating", 5 means "Violation Score", and 6 means "Vehicle Usage".&#x20;
* **eventName:** this key-value pair represents the name or description of the event as a string                value, e.g. **"Harsh and sudden acceleration"**.
* **latitude:** this key-value pair represents the latitude coordinate as a numeric value, e.g. **50.76787**.
* **longitude:** this key-value pair represents the longitude coordinate as a numeric value, e.g. **6.1042366**.



### <mark style="color:green;">**Get Last Trip**</mark>

The endpoint is designed to handle requests for retrieving or fetching the information of the last or most recent trip recorded in the system. It allows users to access details about the latest trip they have taken or the most recently recorded trip in the system.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/last" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of last trip properties, including:

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**craeteDate:** this property represents the date and time when a trip was created which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS", and is expected to be a string value, e.g. **"2023-07-25T12:12:09.2115705"**.

**startDateTime:** the startDatetime property represents the date and time when a trip starts. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T15:41:45.282"**.

**endDateTime:** this property represents the date and time when a trip ends. It is formatted as ""yyyy-MM-dd'T'HH:mm:ss.SSS", and it is expected to be a string value, e.g. **"2023-07-25T15:41:57.481"**.

**duration:** the duration property is an object that contains sub-properties representing the duration of the trip. These sub-properties include ticks, days, hours, milliseconds, minutes, and seconds. Each sub-property is expected to be a numeric value, e.g. **"00:00:12.1990000"**.

**origin:** the origin property represents the origin location. It is expected to be a string value, e.g. **"North Rhine-Westphalia, Aachen, Kalkofen"**.

**destination:** the destination property represents the destination location. It is expected to be a string value, e.g. **"North Rhine Westphalia, Aachen, Ponttor"**.

**originPlace:** this property likely represents the name or identifier of the origin place. It is expected to be a string value, e.g. **"Aachen"**.

**destinationPlace:** this property likely represents the name or identifier of the destination place. It is expected to be a string value, e.g. **"Aachen"**.

**score:** the score property likely represents a score gotten from a trip that is between 0 to 100. It is expected to be a numeric value, e.g. **70**.

**gpsInfo:** the gpsInfo property is an array containing GPS information, which includes

* **gpsTime:** the gpsTime property represents the date and time of the GPS information, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS". It is expected to be a string value, e.g. **"2023-08-29T20:54:56.833+00:00"**.
* **altitude:** the altitude property represents the altitude value. It is expected to be a numeric value, e.g. **215.5**.
* **latitude:** the latitude property represents the latitude coordinate. It is expected to be a numeric value, e.g. **50.767002**.
* **longitude:** the longitude property represents the longitude coordinate. It is expected to be a numeric value, e.g. **6.1035986**.
* **speed:** the speed property represents the speed value. It is expected to be a string value, e.g. **38**.&#x20;
* **climb:**  the climb property represents the climb value. It is expected to be a string value, e.g. **0.0**.
* **course:** the course property represents the course value. It is expected to be a string value, e.g. **280.8201**.
* **epx:** the epx property represents the estimated position error along the X-axis. It is expected to be a string value, e.g. **N/A**.
* **epy:** the epy property represents the estimated position error along the Y-axis. It is expected to be a string value, e.g. **N/A**.
* **epv:** the epv property represents the estimated position error vertically. It is expected to be a string value, e.g. **N/A**.
* **eps:** the eps property represents the estimated speed error. It is expected to be a string value, e.g. **N/A**.
* **epc:** the epc property represents the estimated climb error. It is expected to be a string value, e.g. **N/A**.
* **epd:** the epd property represents the estimated course error. It is expected to be a string value, e.g. **N/A**.



### <mark style="color:green;">Get File Chunk Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the status of file chunks related to a trip. It allows users to check the status of individual or multiple file chunks that make up a larger file associated with the trip.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/fileChunkStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**TripId:** the TripId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**TripFileType:** it specifies the type of uploading file, and it is expected to be a numeric value, e.g. **1**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO will return **0**, IMU will return **1**, GPS will return **2**, TTC will return **4**, and MATRIX will return **5**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of file chunk status properties, including:

**fileChunkIds:** the fileChunkIds property is an array that contains the identifiers or references for the file chunks associated with the upload process, and it is expected to be a list of numeric values, e.g. **\[0, 1, 2]**.

**chunkSize:** the chunkSize property represents the size of each file chunk in bytes, and it is expected to be a numeric value, e.g. **10485760**.&#x20;

**fileId:** the fileId property is the identifier or reference for the uploaded file, and it is expected to be a numeric value, e.g. **5596**.

**isUploaded:** the isUploaded property is a Boolean value that indicates whether the file has been successfully uploaded, e.g. **true**.

**uploadPercent:** the uploadPercent property represents the progress or percentage of the upload process, and it is expected to be a numeric value, e.g. **100**.



### <mark style="color:green;">Get Trip Event Stats By ID</mark>

The endpoint is designed to handle requests for retrieving or fetching event statistics related to a specific trip. It allows users to access aggregated data or metrics about various events that occurred during the trip.

{% swagger src="../../.gitbook/assets/swagger (3).json" path="/api/v4/Trip/{id}/eventStats" method="get" expanded="true" %}
[swagger (3).json](<../../.gitbook/assets/swagger (3).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains an array of a list of event states’ properties, including:

**eventType:** the eventType property represents the type of event that occurred, and it is expected to be a numeric value, e.g. **3**.&#x20;

<mark style="color:red;">**Note:**</mark> The value 0 suggests that it is a "Harsh Accel", 1 means "Harsh Brake", 2 means "Harsh Corner", 3 means "Speeding", 4 means "TailGating", 5 means "Violation Score", and 6 means "Vehicle Usage".&#x20;

<mark style="color:red;">**Note:**</mark> if evetntType is "Speeding" or "TailGating", we just need to have events.value.

If evetntType is "Harsh Accel", "Harsh Brake" or  "Harsh Corner", we just need to have events.time & events.location.

If evetntType is "Vehicle Usage", we just need to have rideTimeEvent.

If else, we just need to have events.time & events.value.

**eventName:** this key-value pair represents the name or description of the event as a string value, e.g. **"Harsh and sudden acceleration"**.

**score:** the score property represents a score associated with the event. It is expected to be a numeric value, e.g. **19**.

**scorePercentile:** the scorePercentile property represents the percentile rank of the score achieved for the event.  It is expected to be a numeric value, e.g. **95**.

**events:** the events property is an array that contains objects representing specific events. Each event object includes properties such as time, value, latitude, longitude, and location. These properties provide details about the event's time, value, GPS coordinates, and location.

* **time:** this key-value pair represents the time of the event, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS". It is expected to be a string value, e.g. **"2023-08-29T20:56:27.832Z".**
* **value:** this key-value pair represents the value associated with the event, and it is expected to be a string value, e.g. **"0.28".**
* **latitude:** this key-value pair represents the latitude coordinate. It is expected to be a numeric value, e.g. **50.76787.**
* **longitude:** this key-value pair represents the longitude coordinate. It is expected to be a numeric value, e.g. **6.1035986.**
* **location:** this key-value pair represents the location associated with the event, and it is expected to be a string value, e.g. **null**.

**eventDetected:** the eventDetected property is an array that contains objects representing detected events. Each detected event object includes properties such as time, latitude, longitude, speedLimit, and yourSpeed. These properties provide details about the detected event's time, GPS coordinates, speed limit, and actual speed.

* **time:** this key-value pair represents the time of the event, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS". It is expected to be a string value, e.g. **"2023-08-29T20:56:01.256Z"**.
* **latitude:** this key-value pair represents the latitude coordinate and is expected to be a numeric value, e.g. **50.767002.**
* **longitude:** this key-value pair represents the longitude coordinate and is expected to be a numeric value, e.g. **6.1042366.**
* **speedLimit:** this key-value pair represents the speed limit associated with the event, and is expected to be a string value, e.g. **30**.
* **yourSpeed:** this key-value pair represents the speed at which the event was detected, and is expected to be a string value, e.g. **31**.

**eventDetectedTailGating:** the eventDetectedTailGating property is an array that contains objects representing detected tailgating events. Each detected tailgating event object includes properties such as time, speedInKmph, ttc, and depth. These properties provide details about the detected tailgating event's time, speed in kilometers per hour, time-to-collision (TTC), and depth.

* **time:** this key-value pair represents the time of the detected tailgating event which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS". It is expected to be a string value, e.g. **"2023-08-29T20:59:08.978Z"**.
* **speedInKmph:** this key-value pair represents the speed at which the tailgating event was detected, measured in kilometers per hour. It is expected to be a string value, e.g. **37.75**.
* **ttc:** this key-value pair represents the Time to Collision (TTC) associated with the tailgating event. It is expected to be a string value, e.g. **0.93**.
* **depth:** this key-value pair represents the depth or severity of the tailgating event, and it is expected to be a string value, e.g. **8.75**.

**rideTimeEvent:** the rideTimeEvent property represents information related to ride time. It includes sub-properties such as totalTime and tripDistance. The totalTime, nightTime and rushHour properties further include sub-properties like hours, minutes, and seconds. The tripDistance property represents the distance covered during the ride.

* **totalTime:** This key-value pair represents the total time of the ride. Inside the "totalTime" object, there are three key-value pairs:&#x20;
  * **hours:** this key-value pair represents the number of hours during the ride time. It is expected to be a numeric value, e.g. **0**.
  * **minutes:** this key-value pair represents the number of minutes during the ride time. It is expected to be a numeric value, e.g. **11**.
  * **seconds:** this key-value pair represents the number of seconds during the ride time. It is expected to be a numeric value, e.g. **50**.
* **nightTime:** this key-value pair represents the total time of the ride at night. Inside the "nightTime" object, there are three key-value pairs:&#x20;
  * **hours:** this key-value pair represents the number of hours during the ride time at night. It is expected to be a numeric value, e.g. **00**.
  * **minutes:** this key-value pair represents the number of minutes during the ride time at night. It is expected to be a numeric value, e.g. **11**.
  * **seconds:** this key-value pair represents the number of seconds during the ride time at night. It is expected to be a numeric value, e.g. **00**.
* **rushHour:** this key-value pair represents an object that captures information about the rush hour duration during the ride. Inside the "rushHour" object, there are three key-value pairs:&#x20;
  * **hours:** this key-value pair represents the number of hours spent during rush hour. It is expected to be a numeric value, e.g. **00**.
  * **minutes:** this key-value pair represents the number of minutes spent during rush hour. It is expected to be a numeric value, e.g. **00**.
  * **seconds:** this key-value pair represents the number of seconds spent during rush hour. It is expected to be a numeric value, e.g. **00**.
* **tripDistance:** this key-value pair represents the distance of the trip. It is expected to be a string value, e.g. **"3.97 km"**.



### <mark style="color:green;">Get Files Of Completed Status</mark>

The endpoint is designed to handle requests for retrieving or fetching the completion status of files related to a trip. It allows users to check whether the files associated with the trip have been completed or not.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/filesCompletedStatus" method="get" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**tripId:** the tripId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of properties for the files’ completed status, including:

**isCompleted:** the isCompleted property is a Boolean value that indicates whether the process or operation has been completed, e.g. **true**.

**message:** the message property provides a string value that typically includes additional information or a status message related to the completion of the process. The actual value of the string would depend on the specific implementation or context of the endpoint. It may contain details about the completed process, any relevant information or instructions, or an indication of success or failure. It is expected to be a string value.



### <mark style="color:green;">Get Total Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the total carbon emissions or carbon footprint of a trip or journey. It allows users to access information about the environmental impact in terms of carbon emissions resulting from a specific trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/totalCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of total carbon property, which is:

**carbon:** the carbon property represents the amount of carbon emissions associated with a particular process, activity, or calculation, and the unit of measurement is Kilogram. It is expected to be a numeric value, e.g. **68.42**.



### <mark style="color:green;">Get Last Trip's Carbon</mark>

The endpoint is designed to handle requests for retrieving or fetching the carbon emissions or carbon footprint of the last or most recent trip recorded in the system. It allows users to access information about the environmental impact in terms of carbon emissions resulting from the most recent trip.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/lastTripCarbon" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of last trip carbon properties, including:

**carbon:** the carbon property represents the amount of carbon emissions associated with a particular process, activity, or calculation, and the unit of measurement is Kilogram. It is expected to be a numeric value, e.g. **0.72**.&#x20;

**lastUpdate:** the lastUpdate property indicates the date and time when the carbon emission information was last updated, which is formatted as "yyyy-MM-dd'T'HH:mm:ss.SSS" . It is expected to be a string value, e.g. **"2023-08-29T20:54:56.836"**.&#x20;



###

