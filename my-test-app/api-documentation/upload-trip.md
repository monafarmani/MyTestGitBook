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

# Upload Trip

## **Overview**

The "Upload Trip" functionality allows users to upload trip data to our API, enabling them to store and process their travel-related information. This feature is essential for users who need to securely transmit their trip details and leverage our API's capabilities for further analysis and processing.

For uploading trips, it is necessary to take some steps in order. These steps are listed below respectively.

Every trip creates a folder in which various files are stored, like <mark style="color:red;">**video.mp4**</mark>, <mark style="color:red;">**imu.csv**</mark>, <mark style="color:red;">**gps.csv**</mark>, <mark style="color:red;">**ttc.csv**</mark>, <mark style="color:red;">**matrix.txt**</mark>. Besides, we need to create another file under the name of <mark style="color:red;">**trip.txt**</mark> which includes trip data like "tripId = 0", and "isCompleted = false" to check whether the trip was uploaded.

<mark style="color:red;">**Note:**</mark> We are going to deal with the files that have not been uploaded yet.

All the files mentioned above must be uploaded for recording the trip. For this purpose, a request will be sent to the API to get [the files completed status](upload-trip.md#get-files-of-completed-status), then the "isCompleted" property should be checked. If it's **true**, it means the files are completed properly, and the data of the <mark style="color:red;">**trip.txt**</mark> can be updated. So, if there is another trip, we will check uploading the files of that trip.

<mark style="color:red;">**Note:**</mark> The trips must be sent in order. It means uploading the files of the former trip must be done, then the next trip files can be checked.

<mark style="color:purple;">**Step 1:**</mark> If the "isCompleted" property is **false**, it means either no files were uploaded or some files were uploaded, but the uploading process wasn't completed. If no files were uploaded, and the **tripId** property inside the <mark style="color:red;">**trip.txt**</mark> equals **0**, we need to send a request to the API to [create a trip](upload-trip.md#create-trip) and update **tripId** in <mark style="color:red;">**trip.txt**</mark>. If else, the next steps must be taken.

<mark style="color:purple;">**Step 2:**</mark> For all the files we have in the folder, we should check whether each one has been uploaded or not. For this purpose and avoiding reuploading the files, we request the API to get [the status of file chunks](upload-trip.md#get-file-chunk-status) and study the **fileId** (**fileManagerId**) of the desired file. The null fileId property indicates that the fileManagerId has not been created yet.

<mark style="color:red;">**Note:**</mark> These properties can be used in step 4 for sending the chunked files later.

* **fileChunkIds:** the list of the chunks' indexes that are uploaded properly.
* **chunkSize:** the size of each size, which is expected to be a numeric value.

<mark style="color:purple;">**Step 3:**</mark> In case of receiving a null value for **fileId**, we will send a request to the API to [start uploading](upload-trip.md#upload-start), in which we will give the specifications of the desired file and receive the **fileManagerId**.&#x20;

<mark style="color:purple;">**Step 4:**</mark> After getting the fileManagerId property, send the uploaded files in chunks through the [upload chunks](upload-trip.md#upload-chunks) endpoint and check the Response of the API. If the mergeStatus property is **true**, it means all the chunks are sent and merged on the server properly.

<mark style="color:red;">**Note:**</mark> The indexes should be sent through the upload chunks endpoint that do not exist in fileChunkIds list.

<mark style="color:purple;">**Step 5:**</mark> To make sure that all the files have been uploaded, we send a request to the API to check the [completion of a trip's file upload process](upload-trip.md#complete-uploading), and receive a Boolean Response, which **true** means it's uploaded completely. Here, update the isCompleted property of <mark style="color:red;">**trip.txt**</mark> to **true** too.



## Endpoints

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

The provided endpoint response contains several properties, including

**isCompleted:** the isCompleted property is a Boolean value that indicates whether the process or operation has been completed, e.g. **true**.

**message:** the message property provides a string value that typically includes additional information or a status message related to the completion of the process. The actual value of the string would depend on the specific implementation or context of the endpoint. It may contain details about the completed process, any relevant information or instructions, or an indication of success or failure. It is expected to be a string value.



### <mark style="color:green;">**Create Trip**</mark>&#x20;

The endpoint is designed to handle requests for creating a new trip or journey within the system.&#x20;

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/Trip/createTrip" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property which is: &#x20;

**tripId:** the tripId property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.&#x20;



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

The provided endpoint response contains several properties, including

**fileChunkIds:** the fileChunkIds property is an array that contains the identifiers or references for the file chunks associated with the upload process, and it is expected to be a list of numeric values, e.g. **\[0, 1, 2]**.

**chunkSize:** the chunkSize property represents the size of each file chunk in bytes, and it is expected to be a numeric value, e.g. **10485760**.&#x20;

**fileId:** the fileId property is the identifier or reference for the uploaded file, and it is expected to be a numeric value, e.g. **5596**.

**isUploaded:** the isUploaded property is a Boolean value that indicates whether the file has been successfully uploaded, e.g. **true**.

**uploadPercent:** the uploadPercent property represents the progress or percentage of the upload process, and it is expected to be a numeric value, e.g. **100**.



### <mark style="color:green;">Upload Start</mark>

The endpoint is designed to handle requests for initiating the start of a file upload process related to a trip. It allows users to begin uploading a file or multiple files associated with the trip to the server.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadStart" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Request Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Query Parameters</mark>

**ItemId:** the itemId (**tripId**) property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**chunkCount:** the chunk count represents the total number of the smaller chunks that make up the entire file, and it is expected to be a numeric value, e.g. **10**.

**FileType:** it specifies the type of uploading file, and it is expected to be an numeric value, e.g. **0**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO will return **0**, IMU will return **1**, GPS will return **2**, TTC will return **4**, and MATRIX will return **5**.

**FileExtension:** it specifies the type of file extension, and it is expected to be an numeric value, e.g. **1**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO\_MP4 will return **1**, TEXT\_CSV will return **3**, and TEXT\_TXT will return **4**.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a property which is:&#x20;

**fileManagerId:** the fileManagerId property represents an identifier or reference to a file manager that is going to be used in [Upload Chunks](upload-trip.md#upload-chunks). It is expected to be a numeric value, e.g. **1002**.



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

**FileType:** it specifies the type of uploading file, and it is expected to be an numeric value, e.g. **0**.&#x20;

<mark style="color:red;">**Note:**</mark> VIDEO will return **0**, IMU will return **1**, GPS will return **2**, TTC will return **4**, and MATRIX will return **5**.

**FileChunk:** this property represents the content of a file chunk, and it is expected to be a file value.

<mark style="color:red;">**Note:**</mark> the type content for HttpHeaders can be either ContntType.VIDEO\_MP4 or ContntType.TEXT\_CSV.&#x20;

<mark style="color:red;">**Note:**</mark> the value for HttpHeaders in ContentDisposition should be "filename="${fileName}"".

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties, including

**id:** the id property represents an identifier or reference to a trip. It is expected to be a numeric value, e.g. **1002**.

**mergeStatus:** the mergeStatus property indicates the status of a merge operation, and it is expected to be a Boolean value. When set to **true**, it suggests that the merge process has been successfully completed.

**uploadPercent:** the uploadPercent property represents the progress or percentage of an upload process. It is expected to be a numeric value, e.g. **30**.



### <mark style="color:green;">Complete Uploading</mark>

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
