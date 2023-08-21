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

# Emergency Contact

### <mark style="color:blue;">User Emergency Contact</mark>

<mark style="color:green;">**Add Emergency Contact :**</mark> The endpoint is designed to handle requests for adding or updating the emergency contact information associated with a user's profile.&#x20;

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**firstName :** the `firstName` property represents the person's first name of an emergency contact. It is expected to be a string value, e.g. **"Sarah"**

**lastName :** the `lastName` property represents the person's last name of an emergency contact. It is also expected to be a string value, e.g. **"Williams"**

**phoneNumber :** the `phoneNumber` property represents the person's phone number of an emergency contact. It is expected to be a string value, e.g. **"+49\_01747707508"**

**email :** the `email` property represents the person's email address of an emergency contact. It is also expected to be a string value, e.g. **"sarahwilliams@gmail.com"**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that emergency contact information is updated.



<mark style="color:green;">**Get Emergency Contact Information :**</mark> The endpoint is designed to handle requests for retrieving or fetching the emergency contact information associated with a user's profile. It allows users to retrieve details about the designated emergency contact person.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/emergencyContact" method="get" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**firstName :** the `firstName` property represents the person's first name. It is expected to be a string value, e.g. **"Sarah"**

**lastName :** the `lastName` property represents the person's last name. It is also expected to be a string value, e.g. **"Williams"**

**phoneNumber :** the `phoneNumber` property represents the person's phone number. It is expected to be a string value, e.g. **"+49\_01747707508"**

**email :** the `email` property represents the person's email address. It is also expected to be a string value, e.g. **"sarahwilliams@gmail.com"**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.



### <mark style="color:blue;">User First time Use initial</mark>

&#x20;<mark style="color:green;">**Initial :**</mark> The endpoint is designed to handle requests for updating the initial information or settings associated with a user's profile. It allows users to modify their initial profile details or configuration.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that getting initial information from user is completed.



### <mark style="color:blue;">Report Accident</mark>

<mark style="color:green;">**Accident :**</mark> The endpoint is designed to handle requests for reporting an accident related to a user. It allows users to submit information about an accident they have experienced or been involved in.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/user/accident" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that an accident is reported and a message would be sent to the [emergency contact](emergency-contact.md#user-emergency-contact).