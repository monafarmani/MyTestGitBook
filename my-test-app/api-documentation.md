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

# 📖 API Documentation

## Overview

API documentation serves as a reference guide for developers and users to understand how to interact with an API effectively. It provides detailed explanations, instructions, and examples on how to make API requests, handle responses, and utilize various features and functionalities.

Our API documentation is generated using **Swagger**, an open-source framework that simplifies the process of designing, building, documenting, and consuming APIs (Application Programming Interfaces). It provides a set of tools and specifications that help developers describe, document, and visualize the structure and behavior of their APIs.



## Endpoints

Here are the list of all the available endpoints or routes provided by the API

## <mark style="color:purple;">Login/Register And Verify</mark>

**1. Check Identity:** The endpoint allows users to submit identity-related information or credentials to confirm the user's identity.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/checkIdentity" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username:** the phone number of the user e.g. **+49\_01747707607**

#### <mark style="color:orange;">**Response**</mark>

It returns a Boolean, and if it's true it could indicate that the user is authenticated, then a message would be sent for verification.

**Note:** If the telephone number has been previously registered, it uses the corresponding data; otherwise, it adds a new user.



**2. Verify:** The endpoint allows users to submit data or credentials for verification purposes.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/verify" method="post" expanded="true" fullWidth="false" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username:** the phone number of the user that used in [Check Identity](api-documentation.md#api-v1-user-checkidentity) e.g. **+49\_01747707607**

**verifyCode:**  the 5 number code which is send through messages sent e.g. **12345**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including&#x20;

**`userName`**: This property likely represents the user phone number. It is expected to be a string value.

**`token`**: The `token` property typically represents an authentication token or access token associated with the user session. It is commonly used for subsequent API requests to authenticate and authorize the user.

**`firstName`**: This property represents the user's first name. It is expected to be a string value.

**`lastName`**: The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`**: This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`**: The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`isInitialized`**: The `isInitialized` property is a Boolean value (`true` or `false`). It shows whether the user uses the app for the first time or not.



## <mark style="color:purple;">User</mark>

### <mark style="color:blue;">Current User</mark>

The endpoint is designed to handle requests for retrieving or fetching the information of the currently authenticated user. It allows users to access their own profile or account details.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/currentUser" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several key-value pairs representing different properties. Here's the breakdown of each property and its potential meaning:

`userName`: This property likely represents the username associated with the user's account. It is expected to be a string value.

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`profileImagePath`:** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "2023-08-15T11:12:39.091Z", which indicates the date and time in ISO 8601 format. The "Z" at the end indicates that the time is in UTC (Coordinated Universal Time).

**`gender`:** The `gender` property represents the user's gender. In this case, it is represented as a numeric value (`0`). The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Common conventions include `0` for unspecified, `1` for male, and `2` for female.

**`isInitialized`:** The `isInitialized` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the user account has been fully initialized or set up. In this case, `isInitialized` being `true` suggests that the user account has completed the necessary initialization steps.

### <mark style="color:blue;">User profile</mark>

**1.profile:** The endpoint is designed to handle requests for updating or modifying the profile information of a user. It allows users to make changes to their profile data, such as their name, email address, contact information, or any other relevant details.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/User/profile" method="patch" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several key-value pairs representing different properties. Here's the breakdown of each property and its potential meaning:

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "2023-08-15T11:12:39.979Z", which indicates the date and time in ISO 8601 format. The "Z" at the end indicates that the time is in UTC (Coordinated Universal Time).

**`gender`:** The `gender` property represents the user's gender. In this case, it is represented as a numeric value (`0`). The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Common conventions include `0` for unspecified, `1` for male, and `2` for female.

**`companyCode`:** This property represents a company code associated with the user. It is expected to be a string value.





**2.Profile Image:** The endpoint is designed to handle requests for uploading or updating the profile image of a user. It allows users to provide an image file representing their profile picture or avatar.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/uploadProfileImage" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**profileImage:**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several key-value pairs representing different properties. Here's the breakdown of each property and its potential meaning:

**`userName`:** This property likely represents the username associated with the user's account. It is expected to be a string value.

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`profileImagePath`:** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "2023-08-15T11:12:36.807Z", which indicates the date and time in ISO 8601 format. The "Z" at the end indicates that the time is in UTC (Coordinated Universal Time).

**`gender`:** The `gender` property represents the user's gender. In this case, it is represented as a numeric value (`0`). The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Common conventions include `0` for unspecified, `1` for male, and `2` for female.

### <mark style="color:blue;">User car</mark>

**1. Car Model :** The endpoint is designed to handle requests for adding or updating the car model information associated with a user's profile. It allows users to provide details about the car model they own or use.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**carModelName:**

&#x20;**carBrandName:**

&#x20;**license:**&#x20;

&#x20;**yearOfProduction:**

&#x20;**mileage:**&#x20;

#### <mark style="color:orange;">**Response**</mark>



**2. Select Car Model:** The endpoint is designed to handle requests for selecting or choosing a specific car model for a user's profile. It allows users to indicate their preference or choice of a particular car model.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel/select" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:**

#### <mark style="color:orange;">**Response**</mark>



**3. Car Models:** The endpoint is designed to handle requests for retrieving or fetching the car models associated with a user's profile. It allows users to retrieve information about the car models they own or use.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON array containing a single object. Here is the breakdown of the properties within the object and their potential meanings:

**`id`:** This property likely represents the ID of the car. It is expected to be a numeric value (`0` in this case).

**`carModelId`:** The `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value (`0` in this case).

**`carBrandId`:** This property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value (`0` in this case).

**`carName`:** The `carName` property represents the name or identifier of the car. It is expected to be a string value.

**`carModel`:** This property represents the model of the car. It is expected to be a string value.

**`license`:** The `license` property represents the license plate number or identifier of the car. It is expected to be a string value.

**`yearOfProduction`:** This property represents the year of production for the car. It is expected to be a numeric value (`0` in this case).

**`mileage`:** The `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case).

**`isSelected`:** The `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose.



**4. Car Models by Id:** The endpoint is designed to handle requests for retrieving or fetching a specific car model associated with a user's profile. It allows users to retrieve detailed information about a particular car model based on its unique identifier.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels/{id}" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON object containing properties related to a car. Here's the breakdown of each property and its potential meaning:

**`id`:** This property likely represents the ID of the car. It is expected to be a numeric value (`0` in this case).

**`carModelId`:** The `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value (`0` in this case).

**`carBrandId`:** This property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value (`0` in this case).

**`carName`:** The `carName` property represents the name or identifier of the car. It is expected to be a string value.

**`carModel`:** This property represents the model of the car. It is expected to be a string value.

**`license`:** The `license` property represents the license plate number or identifier of the car. It is expected to be a string value.

**`yearOfProduction`:** This property represents the year of production for the car. It is expected to be a numeric value (`0` in this case).

**`mileage`:** The `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case).

**`isSelected`:** The `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose.





**5. Delete Car Model:** The endpoint is designed to handle requests for deleting the car model information associated with a user's profile. It allows users to remove or delete the car model data that is currently associated with their profile.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="delete" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id:**&#x20;

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:blue;">User Emergency Contact</mark>

**1. Add Emergency Contact:** The endpoint is designed to handle requests for adding or updating the emergency contact information associated with a user's profile. It allows users to provide or modify details about their designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**firstName:**

&#x20;**lastName:**

&#x20;**phoneNumber:**

**email:**

#### <mark style="color:orange;">**Response**</mark>



**2. Get Emergency Contact Information:** The endpoint is designed to handle requests for retrieving or fetching the emergency contact information associated with a user's profile. It allows users to retrieve details about the designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON object containing properties related to a person's information. Here's the breakdown of each property and its potential meaning:

**`firstName`:** The `firstName` property represents the person's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the person's last name. It is also expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the person's phone number. It is expected to be a string value.

**`email`:** The `email` property represents the person's email address. It is also expected to be a string value.





### <mark style="color:blue;">User First time Use initial</mark>

**Initial:** The endpoint is designed to handle requests for updating the initial information or settings associated with a user's profile. It allows users to modify their initial profile details or configuration.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



### <mark style="color:blue;">Report Accident</mark>

The endpoint is designed to handle requests for reporting an accident related to a user. It allows users to submit information about an accident they have experienced or been involved in.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/accident" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



## <mark style="color:purple;">Trip</mark>



The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

The endpoint is designed to handle requests for creating a new trip or journey within the system. It allows users to submit the necessary information and parameters to define and initiate a new trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/createTrip" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the information of the last or most recent trip recorded in the system. It allows users to access details about the latest trip they have taken or the most recently recorded trip in the system.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/last" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for generating a report of trips or journeys. It allows users to retrieve aggregated or summarized information about multiple trips based on certain criteria or filters.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/report" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the driving score information associated with a trip or journey. It allows users to access details about the driving performance or behavior during a specific trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/drivingScore" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving event statistics within a trip report. It allows users to access aggregated information and statistics related to specific events or incidents that occurred during trips or journeys.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/report/eventStats" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the total carbon emissions or carbon footprint of a trip or journey. It allows users to access information about the environmental impact in terms of carbon emissions resulting from a specific trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/totalCarbon" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the carbon emissions or carbon footprint of the last or most recent trip recorded in the system. It allows users to access information about the environmental impact in terms of carbon emissions resulting from the most recent trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/lastTripCarbon" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching performance metrics or statistics related to a user's trips or journeys. It allows users to access information about their own performance as it pertains to their trips.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/myPerformance" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching GPS data associated with a specific trip. It allows users to access the latitude and longitude coordinates or other relevant GPS information recorded during the trip.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/Trip/{id}/gps" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the status of file chunks related to a trip. It allows users to check the status of individual or multiple file chunks that make up a larger file associated with the trip.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/fileChunkStatus" method="get" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching the completion status of files related to a trip. It allows users to check whether the files associated with the trip have been completed or not.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/filesCompletedStatus" method="get" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for initiating the start of a file upload process related to a trip. It allows users to begin uploading a file or multiple files associated with the trip to the server.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadStart" method="post" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for uploading file chunks of a trip to the server. When a large file needs to be uploaded, it is often split into smaller chunks for efficient and reliable transmission.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadChunks" method="post" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for indicating the completion of a file upload process related to a trip. It allows users to signal that all file chunks associated with the trip have been successfully uploaded.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadComplete" method="post" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching event statistics related to a specific trip. It allows users to access aggregated data or metrics about various events that occurred during the trip.

{% swagger src="../.gitbook/assets/swagger (3).json" path="/api/v4/Trip/{id}/eventStats" method="get" expanded="true" %}
[swagger (3).json](<../.gitbook/assets/swagger (3).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>

### <mark style="color:purple;">others</mark>



The endpoint is designed to handle requests for retrieving or fetching agreements. It allows users to access information about agreements stored in the system or application.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/agreements" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching information about car brands. It allows users to access a list of car brands available in the system or application.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/CarBrand" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching configuration settings or information from the system or application.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Config" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for geocoding addresses or place names.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Map/geoCode" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching a privacy policy from the system or application.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/PrivacyPolicy" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



The endpoint is designed to handle requests for retrieving or fetching terms and conditions information from the system or application.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/terms" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

#### <mark style="color:orange;">**Response**</mark>



## Errors

In case of errors, the API may return the following HTTP status codes along with error responses:

* 400 Bad Request: Invalid request parameters or missing required fields.
* 401 Unauthorized: Missing or invalid API key.
* 404 Not Found: The requested resource does not exist.
* 500 Internal Server Error: An unexpected error occurred on the server.



## Rate Limiting

The API enforces rate limiting to ensure fair usage. Each API key is limited to 100 requests per minute. If the rate limit is exceeded, a response with status code 429 "Too Many Requests" will be returned.



## Support

For any questions or assistance regarding the Android Project API, please contact our support team at [support@example.com](mailto:support@example.com).





