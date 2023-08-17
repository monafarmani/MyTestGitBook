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



### <mark style="color:purple;">User</mark>

The endpoint is designed to handle requests for verifying the identity of a user. It allows users or authorized parties to submit identity-related information or credentials to confirm the user's identity.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/checkIdentity" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for verifying a user's identity, account, or other relevant information. It allows users or authorized parties to submit data or credentials for verification purposes.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/verify" method="post" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



The endpoint is designed to handle requests for updating or modifying the profile information of a user. It allows users to make changes to their profile data, such as their name, email address, contact information, or any other relevant details.

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/User/profile" method="patch" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}



The endpoint is designed to handle requests for uploading or updating the profile image of a user. It allows users to provide an image file representing their profile picture or avatar.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/uploadProfileImage" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for adding or updating the car model information associated with a user's profile. It allows users to provide details about the car model they own or use.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for retrieving or fetching the car models associated with a user's profile. It allows users to retrieve information about the car models they own or use.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



The endpoint is designed to handle requests for retrieving or fetching a specific car model associated with a user's profile. It allows users to retrieve detailed information about a particular car model based on its unique identifier.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels/{id}" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



The endpoint is designed to handle requests for selecting or choosing a specific car model for a user's profile. It allows users to indicate their preference or choice of a particular car model.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel/select" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for creating or updating the car model information associated with a user's profile. It allows users to provide or modify details about the car model they own or use.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="put" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



The endpoint is designed to handle requests for deleting the car model information associated with a user's profile. It allows users to remove or delete the car model data that is currently associated with their profile.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="delete" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



The endpoint is designed to handle requests for retrieving or fetching the emergency contact information associated with a user's profile. It allows users to retrieve details about the designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for adding or updating the emergency contact information associated with a user's profile. It allows users to provide or modify details about their designated emergency contact person or persons.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for reporting an accident related to a user. It allows users to submit information about an accident they have experienced or been involved in.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/accident" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for updating the initial information or settings associated with a user's profile. It allows users to modify their initial profile details or configuration.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for retrieving or fetching the information of the currently authenticated user. It allows users to access their own profile or account details.

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/currentUser" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

### <mark style="color:purple;">Trip</mark>



The endpoint is designed to handle requests for retrieving or fetching information about trips or journeys. It allows users to access details related to various trips that may have been recorded or stored in the system.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for retrieving or fetching information about a specific trip or journey based on its unique identifier. It allows users to access detailed information about a particular trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}



The endpoint is designed to handle requests for creating a new trip or journey within the system. It allows users to submit the necessary information and parameters to define and initiate a new trip.

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/createTrip" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/last" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/report" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/drivingScore" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/report/eventStats" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/totalCarbon" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/lastTripCarbon" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/myPerformance" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/Trip/{id}/gps" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/fileChunkStatus" method="get" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/filesCompletedStatus" method="get" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadStart" method="post" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadChunks" method="post" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/Trip/uploadComplete" method="post" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (3).json" path="/api/v4/Trip/{id}/eventStats" method="get" %}
[swagger (3).json](<../.gitbook/assets/swagger (3).json>)
{% endswagger %}





### <mark style="color:purple;">others</mark>

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/agreements" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/CarBrand" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Config" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Map/geoCode" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/PrivacyPolicy" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/terms" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}











