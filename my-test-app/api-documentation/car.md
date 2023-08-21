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

# User's Car

### <mark style="color:green;">Add</mark> <mark style="color:green;"></mark><mark style="color:green;">**Car Model**</mark>&#x20;

The endpoint is designed to handle requests for adding the car model information associated with user's cars.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/carModel" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**carModelName :** the model name of the user's car and It is expected to be a string value, e.g. **"C200"**

&#x20;**carBrandName :** the brand name of the user's car and It is expected to be a string value, e.g. **"Benz"**

&#x20;**license :** the license plate number  of the user's car and It is expected to be a string value, e.g. **"RAKL 8136"**

&#x20;**yearOfProduction :** the year of production of the user's car and It is expected to be a numeric value, e.g. **2001**

<mark style="color:red;">**Note :**</mark> yearOfProduction must be added between 1900 and current year.

**mileage :** the mileage or distance traveled by the user's car and It is expected to be a numeric value, e.g. **1000**

<mark style="color:red;">**Note :**</mark> the Maximum character in mileage is 9.

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that car model is added.



### <mark style="color:green;">**Select Active Car Model**</mark>&#x20;

The endpoint is designed to handle requests for selecting or choosing a specific car model for a current active user's car.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/carModel/select" method="patch" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id :** The ID of the car which is selected and It is expected to be a numeric value, e.g. **1560**

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that car model is selected.



### <mark style="color:green;">**Get List Of Car Models**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the car models associated with the user.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains a list of car model properties

**id :** this property likely represents the ID of the car. It is expected to be a numeric value, e.g. **2256**

**carModelId :** the `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value, e.g. **80**

**caBrandId :** this property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value, e.g. **3**

**carName :** the `carName` property represents the name or identifier of the car. It is expected to be a string value, e.g. **"Benz"**

**carModel :** this property represents the model of the car. It is expected to be a string value, e.g. **"C200"**

**license:** the `license` property represents the license plate number or identifier of the car. It is expected to be a string value, e.g. **"RAKL 8136"**

**yearOfProduction :** this property represents the year of production for the car. It is expected to be a numeric value, e.g. **2023**

**mileage :** the `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case), e.g. **1000**

**isSelected :** the `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose, e.g. **false**

<mark style="color:red;">**Note :**</mark> just one car can be selected in a list.



### <mark style="color:green;">**Get Car Model By Id**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching a specific car model associated with a user.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModels/{id}" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Parameters</mark>

**id :** The ID of the car and It is expected to be a numeric value, e.g. **2256**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**id :** this property likely represents the ID of the car. It is expected to be a numeric value, e.g. **2256**

**carModelId :** the `carModelId` property likely represents the ID of the car model associated with the car. It is expected to be a numeric value, e.g. **80**

**caBrandId :** this property likely represents the ID of the car brand associated with the car. It is expected to be a numeric value, e.g. **3**

**carName :** the `carName` property represents the name or identifier of the car. It is expected to be a string value, e.g. **"Benz"**

**carModel :** this property represents the model of the car. It is expected to be a string value, e.g. **"C200"**

**license:** the `license` property represents the license plate number or identifier of the car. It is expected to be a string value, e.g. **"RAKL 8136"**

**yearOfProduction :** this property represents the year of production for the car. It is expected to be a numeric value, e.g. **2023**

**mileage :** the `mileage` property represents the mileage or distance traveled by the car. It is expected to be a numeric value (`0` in this case), e.g. **1000**

**isSelected :** the `isSelected` property is a boolean value (`true` or `false`). In the provided response, it is set to `true`. This property typically indicates whether the car is selected or chosen for a particular purpose, e.g. **false**

<mark style="color:red;">**Note :**</mark> just one car can be selected in a list.



### <mark style="color:green;">**Delete Car Model**</mark>

The endpoint is designed to handle requests for deleting the car model information associated with a user.&#x20;

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/User/carModel" method="delete" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**id :** The ID of the car and it is expected to be a numeric value, e.g. **2256**

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that the car is deleted.
