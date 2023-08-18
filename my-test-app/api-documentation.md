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

<mark style="color:green;">**1. Check Identity :**</mark> The endpoint allows users to submit identity-related information or credentials to confirm the user's identity.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/checkIdentity" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username :** the phone number of the user e.g. **+49\_01747707607**

#### <mark style="color:orange;">**Response**</mark>

It returns a Boolean, and if it's true it could indicate that the user is authenticated, then a message would be sent for verification.

**Note :** If the telephone number has been previously registered, it uses the corresponding data; otherwise, it adds a new user.



<mark style="color:green;">**2. Verify :**</mark> The endpoint allows users to submit data or credentials for verification purposes.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/User/verify" method="post" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username :** the phone number of the user that used in [Check Identity](api-documentation.md#api-v1-user-checkidentity) e.g. **+49\_01747707607**

**verifyCode :**  the 5 number code which is send through messages sent e.g. **12345**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including&#x20;

**`userName`:** This property likely represents the user phone number. It is expected to be a string value.

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`profileImagePath`:** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "1999-08-01T00:00:00", which indicates the date and time in ISO 8601 format.

**`gender`:** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified.

**`isInitialized`:** The `isInitialized` property is a Boolean value (`true` or `false`). It shows whether the user uses the app for the first time or not.

**`token`:** The `token` property typically represents an authentication token or access token associated with the user session. It is commonly used for subsequent API requests to authenticate and authorize the user.



## <mark style="color:purple;">User</mark>

### <mark style="color:blue;">Current User</mark>

The endpoint is designed to handle requests for retrieving or fetching the information of the currently authenticated user. It allows users to access their own profile or account details.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/currentUser" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**`userName`:** This property likely represents the user phone number. It is expected to be a string value.

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`profileImagePath`:** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "1999-08-01T00:00:00", which indicates the date and time in ISO 8601 format.

**`gender`:** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified.

**`isInitialized`:** The `isInitialized` property is a Boolean value (`true` or `false`). It shows whether the user uses the app for the first time or not.



### <mark style="color:blue;">User profile</mark>

<mark style="color:green;">**1. Profile :**</mark>  The endpoint is designed to handle requests for updating or modifying the profile information of a user. It allows users to make changes to their profile data, such as their name, email address, contact information, or any other relevant details.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/User/profile" method="patch" expanded="true" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several key-value pairs representing different properties. Here's the breakdown of each property and its potential meaning:

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "1999-08-01T00:00:00", which indicates the date and time in ISO 8601 format.

**`gender`:** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified.

**`companyCode`:** This property represents a company code associated with the user. It is expected to be a string value.





<mark style="color:green;">**2. Profile image :**</mark> The endpoint is designed to handle requests for uploading or updating the profile image of a user. It allows users to provide an image file representing their profile picture or avatar.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/uploadProfileImage" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**profileImage:** its a profile picture or avatar that must be sent by multipart/form-data format.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**`userName`:** This property likely represents the user phone number. It is expected to be a string value.

**`firstName`:** This property represents the user's first name. It is expected to be a string value.

**`lastName`:** The `lastName` property represents the user's last name. It is also expected to be a string value.

**`email`:** This property represents the user's email address. It is expected to be a string value.

**`phoneNumber`:** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value.

**`profileImagePath`:** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL.

**`birthDate`:** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "1999-08-01T00:00:00", which indicates the date and time in ISO 8601 format.

**`gender`:** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified.



### <mark style="color:blue;">User car</mark>

<mark style="color:green;">**1. Car Model :**</mark> The endpoint is designed to handle requests for adding or updating the car model information associated with a user's profile. It allows users to provide details about the car model they own or use.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**carModelName :** the  model name of the user's car e.g. **C200**

&#x20;**carBrandName :** the brand name of the user's car e.g. **Benz**

&#x20;**license :** the license plate number  of the user's car e.g. RAKL **8136**

&#x20;**yearOfProduction :** the year of production of the user's car e.g. **2001**&#x20;

**Note :** yearOfProduction must be added between 1900 and current year.

**mileage :** the mileage or distance traveled by the user's car e.g. **1000**

**Note :** the Maximum character in mileage is 9.

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that car model is added.



<mark style="color:green;">**2. Select Car Model :**</mark> The endpoint is designed to handle requests for selecting or choosing a specific car model for a user's profile. It allows users to indicate their preference or choice of a particular car model.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel/select" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id :** The id of the car which is selected.

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that car model is selected.



<mark style="color:green;">**3. Car Models :**</mark> The endpoint is designed to handle requests for retrieving or fetching the car models associated with a user's profile. It allows users to retrieve information about the car models they own or use.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**`id`:** this property likely represents the ID of the car. It is expected to be a numeric value.

**`carModelId`:** the `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value .

**`carBrandId`:** this property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value .

**`carName`:** the `carName` property represents the name or identifier of the car. It is expected to be a string value.

**`carModel`:** this property represents the model of the car. It is expected to be a string value.

**`license`:** the `license` property represents the license plate number or identifier of the car. It is expected to be a string value.

**`yearOfProduction`:** this property represents the year of production for the car. It is expected to be a numeric value .

**`mileage`:** the `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case).

**`isSelected`:** the `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose.

**Note :** just one car can be selected in a list.



<mark style="color:green;">**4. Car Models by Id :**</mark> the endpoint is designed to handle requests for retrieving or fetching a specific car model associated with a user's profile. It allows users to retrieve detailed information about a particular car model based on its unique identifier.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels/{id}" method="get" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id :** The ID of the car

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**`id`:** this property likely represents the ID of the car. It is expected to be a numeric value.

**`carModelId`:** the `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value .

**`carBrandId`:** this property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value .

**`carName`:** the `carName` property represents the name or identifier of the car. It is expected to be a string value.

**`carModel`:** this property represents the model of the car. It is expected to be a string value.

**`license`:** the `license` property represents the license plate number or identifier of the car. It is expected to be a string value.

**`yearOfProduction`:** this property represents the year of production for the car. It is expected to be a numeric value .

**`mileage`:** the `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case).

**`isSelected`:** the `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose.

**Note :** just one car can be selected in a list.



<mark style="color:green;">**5. Delete Car Model:**</mark> The endpoint is designed to handle requests for deleting the car model information associated with a user's profile. It allows users to remove or delete the car model data that is currently associated with their profile.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="delete" expanded="true" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id :** the ID of the car

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that car is deleted.

### <mark style="color:blue;">User Emergency Contact</mark>

<mark style="color:green;">**1. Add Emergency Contact :**</mark> The endpoint is designed to handle requests for adding or updating the emergency contact information associated with a user's profile. It allows users to provide or modify details about their designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**firstName :** first name of the emergency contact

&#x20;**lastName :** last name of the emergency contact

&#x20;**phoneNumber :** phone  number of the emergency contact

**email :** email of the emergency contact

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that emergency contact information is recorded.



<mark style="color:green;">**2. Get Emergency Contact Information :**</mark> The endpoint is designed to handle requests for retrieving or fetching the emergency contact information associated with a user's profile. It allows users to retrieve details about the designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response appears to be a JSON object containing properties related to a person's information. Here's the breakdown of each property and its potential meaning:

**`firstName`:** the `firstName` property represents the person's first name. It is expected to be a string value.

**`lastName`:** the `lastName` property represents the person's last name. It is also expected to be a string value.

**`phoneNumber`:** the `phoneNumber` property represents the person's phone number. It is expected to be a string value.

**`email`:** the `email` property represents the person's email address. It is also expected to be a string value.





### <mark style="color:blue;">User First time Use initial</mark>

&#x20;The endpoint is designed to handle requests for updating the initial information or settings associated with a user's profile. It allows users to modify their initial profile details or configuration.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that getting initial information from user is completed .



### <mark style="color:blue;">Report Accident</mark>

The endpoint is designed to handle requests for reporting an accident related to a user. It allows users to submit information about an accident they have experienced or been involved in.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/accident" method="post" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that an accident is reported and a message would be sent to the [emergency contact](api-documentation.md#user-emergency-contact) .

## <mark style="color:purple;">Trip</mark>



The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Query Parameters</mark>

**keyword :**&#x20;

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response is a JSON array containing a single object. Here's the breakdown of each property within the object and their potential meanings:

**`id`:** This property likely represents the ID of the object or item. It is expected to be a numeric value (`0` in this case).

**`score`:** The `score` property likely represents a score or rating associated with the object. It is expected to be a numeric value (`0` in this case).

**`isCompleted`:** The `isCompleted` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the object or associated task is completed.

**`createDate`:** This property represents the date and time when the object or item was created. In the provided response, it is formatted as "2023-08-15T11:12:36.799Z", indicating the date and time in ISO 8601 format with UTC (Coordinated Universal Time).

**`originAddress`:** The `originAddress` property likely represents the address of the origin location. It is expected to be a string value.

**`originPostalCode`:** This property represents the postal code associated with the origin location. It is expected to be a string value.

**`originLocality`:** The `originLocality` property represents the locality or city of the origin location. It is expected to be a string value.

**`originPlace`:** This property likely represents the name or identifier of the origin place. It is expected to be a string value.

**`originRegion`:** The `originRegion` property represents the region or state of the origin location. It is expected to be a string value.

**`destinationAddress`:** The `destinationAddress` property represents the address of the destination location. It is expected to be a string value.

**`destinationPostalCode`:** This property represents the postal code associated with the destination location. It is expected to be a string value.

**`destinationLocality`:** The `destinationLocality` property represents the locality or city of the destination location. It is expected to be a string value.

**`destinationPlace`:** This property likely represents the name or identifier of the destination place. It is expected to be a string value.

**`destinationRegion`:** The `destinationRegion` property represents the region or state of the destination location. It is expected to be a string value.

**`startDateTime`:** The `startDateTime` property represents the date and time when the object or item's activity or event starts. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**`endDateTime`:** This property represents the date and time when the object or item's activity or event ends. It is formatted as "2023-08-15T11:12:36.799Z" in ISO 8601 format with UTC.

**`duration`:** The `duration` property is an object that contains sub-properties representing the duration of the object or item. These sub-properties include `ticks`, `days`, `hours`, `milliseconds`, `minutes`, and `seconds`. Each sub-property is expected to be a numeric value (`0` in this case).



The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" expanded="true" %}
[swagger.json](../.gitbook/assets/swagger.json)
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





