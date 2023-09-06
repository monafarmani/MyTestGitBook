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

The primary purposes of API documentation are understanding API capabilities, integration guidance, code examples, parameter definitions, error handling, versioning and deprecation**,** testing and debugging**,** and compliance and security.



## Endpoints

Endpoints are an integral part of the client-server communication model. In this model, the client (such as a web browser or a mobile application) sends requests to the server, and the server responds with the requested data or performs the requested action. The endpoint acts as the destination or target for these requests.

Endpoints are typically associated with a specific HTTP method, such as GET, POST, PUT, DELETE, etc., which indicates the type of operation to be performed on the resource. For example, a GET request to an endpoint retrieves data, while a POST request submits new data to be processed.

Here is the list of all the available endpoints or routes provided by the API :

#### [Authentication](api-documentation/authentication.md)

#### [User](api-documentation/user.md)

#### [Car](api-documentation/car.md)

#### [Trip](api-documentation/trip.md)

#### [Emergency Contact](api-documentation/emergency-contact.md)

#### [Settings](api-documentation/settings.md)



## Errors

In case of errors, the API may return the following HTTP status codes along with error responses:

* 400 Bad Request: Invalid request parameters or missing required fields.
* 401 Unauthorized: Missing or invalid API key.
* 404 Not Found: The requested resource does not exist.
* 500 Internal Server Error: An unexpected error occurred on the server.
