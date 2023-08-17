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

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/checkIdentity" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/verify" method="post" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (2).json" path="/api/v3/User/profile" method="patch" %}
[swagger (2).json](<../.gitbook/assets/swagger (2).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/uploadProfileImage" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

It allows users to upload a new image file to replace their existing profile image in the system



{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

The endpoint is designed to handle requests for adding or associating a car model with a user's profile. It allows users to specify the details of their car model, such as the make, model, year, and other relevant information.



{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels/{id}" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}



{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/carModel/select" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

The endpoint is designed to handle requests for selecting or setting a particular car model as the chosen model for a user. It allows users to specify the car model they prefer or want to associate with their user profile.



{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="put" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="delete" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

The endpoint is designed to handle requests for retrieving the emergency contact details associated with a user's profile. It allows users or authorized parties to access the contact information of the user's designated emergency contact(s) in case of an emergency situation.



{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

The endpoint is designed to handle requests for adding or updating the emergency contact details associated with a user's profile. It allows users to provide or modify the contact information of their designated emergency contact(s) to be used in case of an emergency situation.



{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/accident" method="post" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

The endpoint is designed to handle requests for reporting or documenting an accident involving a user. It allows users to provide information about the accident, such as the date, time, location, description, and any other relevant details.



{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger (1).json" path="/api/v2/User/currentUser" method="get" %}
[swagger (1).json](<../.gitbook/assets/swagger (1).json>)
{% endswagger %}

### <mark style="color:purple;">Trip</mark>

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/swagger.json" path="/api/v1/Trip/{id}" method="get" %}
[swagger.json](../.gitbook/assets/swagger.json)
{% endswagger %}

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











