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

# User

### <mark style="color:green;">Update</mark> <mark style="color:green;"></mark><mark style="color:green;">**Profile**</mark>

The endpoint is designed to handle requests for updating or modifying the profile information of a user. It allows users to make changes to their profile data, such as their name, email address, contact information, or any other relevant details.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/User/profile" method="patch" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**firstName :** first name of the user and It is expected to be a string value, e.g.**"David"**

**lastName :** last name of the user and It is expected to be a string value. e.g. "**Smith"**

**email :** email of the user and It is expected to be a string value, e.g. **"DavidSmith@gmail.com "**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.

**birthDate :** The `birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "yyyy-MM-dd", which indicates the date and time in ISO 8601 format. e.g. **"1999-08-02"**

**gender :** gender of the user which is Int :  **0** is used for female,**`1`**for male and **2** for unspecified, e.g. **1**

**companyCode :** This property represents a company code associated with the user. It is expected to be a string value.&#x20;

<mark style="color:red;">**Note :**</mark> company code is either null or String

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including&#x20;

**username :** This property likely represents the user phone number. It is expected to be a string value, e.g. **"+49\_01747707607"**

**firstName :** This property represents the user's first name. It is expected to be a string value, e.g.**"David"**

**lastName :** The `lastName` property represents the user's last name. It is also expected to be a string value, e.g. **"Smith"**

**email :** This property represents the user's email address. It is expected to be a string value, e.g. **"DavidSmith@gmail.com "**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.

**phonenumber :** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value, e.g. **"+49\_01747707607"**

**profileImagePath :** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL, e.g. **"ProfilePic/93/ae316a8c-78e3-4427-9f6c-63a0d37d1d0d.jpg"**

**birthDate :** The`birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "yyyy-MM-ddTHH:mm:ss", which indicates the date and time in ISO 8601 format, e.g. **"1999-08-02T00:00:00"**

**gender :** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified, e.g. **1**



### <mark style="color:green;">**Update Profile Image**</mark>&#x20;

The endpoint is designed to handle requests for uploading or updating the profile image of a user. It allows users to provide an image file representing their profile picture or avatar.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/uploadProfileImage" method="patch" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">Request Body Parameters</mark>

**profileImage :** its a profile picture or avatar that must be sent by multipart/form-data format. It is expected to be a string value.

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including

**username :** This property likely represents the user phone number. It is expected to be a string value, e.g. **"+49\_01747707607"**

**firstName :** This property represents the user's first name. It is expected to be a string value, e.g.**"David"**

**lastName :** The `lastName` property represents the user's last name. It is also expected to be a string value, e.g. **"Smith"**

**email :** This property represents the user's email address. It is expected to be a string value, e.g. **"DavidSmith@gmail.com "**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.

**phonenumber :** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value, e.g. **"+49\_01747707607"**

**profileImagePath :** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL, e.g. **"ProfilePic/93/ae316a8c-78e3-4427-9f6c-63a0d37d1d0d.jpg"**

**birthDate :** The`birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "yyyy-MM-ddTHH:mm:ss", which indicates the date and time in ISO 8601 format, e.g. **"1999-08-02T00:00:00"**

**gender :** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified, e.g. **1**



### <mark style="color:green;">**Update User First-time Use Initial**</mark>&#x20;

The endpoint is designed to handle requests for updating the initial information or settings associated with a user's profile. It allows users to modify their initial profile details or configuration.

<mark style="color:red;">**Note :**</mark> Initial is called after [user's profile data](user.md#profile) &[ user car's data](car.md#car-model) get completed in first time use.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/user/initial" method="patch" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Header Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

If it's true, it means that getting initial information from user is completed.



### <mark style="color:green;">**Get Current User**</mark>&#x20;

The endpoint is designed to handle requests for retrieving or fetching the information of the currently authenticated user. It allows users to access their own profile or account details.

{% swagger src="../../.gitbook/assets/swagger (1).json" path="/api/v2/User/currentUser" method="get" expanded="true" %}
[swagger (1).json](<../../.gitbook/assets/swagger (1).json>)
{% endswagger %}

#### <mark style="color:orange;">Header Parameters</mark>

Authentication Bearer Token

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties including&#x20;

**username :** This property likely represents the user phone number. It is expected to be a string value, e.g. **"+49\_01747707607"**

**firstName :** This property represents the user's first name. It is expected to be a string value, e.g.**"David"**

**lastName :** The `lastName` property represents the user's last name. It is also expected to be a string value, e.g. **"Smith"**

**email :** This property represents the user's email address. It is expected to be a string value, e.g. **"DavidSmith@gmail.com "**

<mark style="color:red;">**Note :**</mark> email can be an empty text. if not, it must be sent by proper format of email.

**phonenumber :** The `phoneNumber` property represents the user's phone number. It is also expected to be a string value, e.g. **"+49\_01747707607"**

**profileImagePath :** This property represents the path or location of the user's profile image. It is expected to be a string value that specifies the image file's location or URL, e.g. **"ProfilePic/93/ae316a8c-78e3-4427-9f6c-63a0d37d1d0d.jpg"**

**birthDate :** The`birthDate` property represents the user's birth date and time. In the provided response, it is formatted as "yyyy-MM-ddTHH:mm:ss", which indicates the date and time in ISO 8601 format, e.g. **"1999-08-02T00:00:00"**

**gender :** The `gender` property represents the user's gender. The specific mapping of numeric values to genders may vary depending on the application or system's implementation. Here 0 is used for female,`1`for male and 2 for unspecified, e.g. **1**

**isInitialized :** The `isInitialized` property is a Boolean value (`true` or `false`). It shows whether the user uses the app for the first time or not, e.g. **true**
