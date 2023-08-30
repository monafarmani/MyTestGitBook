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

# Authentication

### <mark style="color:green;">**Check Identity**</mark>&#x20;

The endpoint allows users to submit identity-related information or credentials to confirm the user's identity.

{% swagger src="../../.gitbook/assets/swagger.json" path="/api/v1/User/checkIdentity" method="post" expanded="true" %}
[swagger.json](../../.gitbook/assets/swagger.json)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username:** the phone number of the user which is expected to be a string value. e.g. **"+49\_01747707607"**

#### <mark style="color:orange;">**Response**</mark>

It returns a Boolean, and if it's true, it could indicate that the user is authenticated, then a message would be sent for verification.

<mark style="color:red;">**Note:**</mark> If the telephone number has been previously registered, it uses the corresponding data otherwise; it adds a new user.



### <mark style="color:green;">**Verify**</mark>&#x20;

The endpoint allows users to submit data or credentials for verification purposes.

{% swagger src="../../.gitbook/assets/swagger (2).json" path="/api/v3/User/verify" method="post" expanded="true" %}
[swagger (2).json](<../../.gitbook/assets/swagger (2).json>)
{% endswagger %}

#### <mark style="color:orange;">Request Body Parameters</mark>

**username:** the phone number of the user that is used in Check Identity and It is expected to be a string value, e.g. **"+49\_01747707607"**

**verifyCode:**  the 5-number code taht is sent through messages and is expected to be a string value, e.g. **"12345"**

#### <mark style="color:orange;">**Response**</mark>

The provided endpoint response contains several properties, including

**username:** this property likely represents the user’s phone number. It is expected to be a string value, e.g. **“+49\_01747707607”**

**firstName:** this property represents the user’s first name. It is expected to be a string value, e.g. **“David”**

**lastName:** the lastName property represents the user’s last name. It is also expected to be a string value, e.g. **“Smith”**

**email:** this property represents the user’s email address. It is expected to be a string value, e.g. **“DavidSmith@gmail.com “**

<mark style="color:red;">**Note:**</mark> email can be an empty text. If not, it must be sent in the proper format of email.

**phonenumber:** the phoneNumber property represents the user’s phone number. It is also expected to be a string value, e.g. **“+49\_01747707607”**

**profileImagePath:** this property represents the path or location of the user’s profile image. It is expected to be a string value that specifies the image file’s location or URL, e.g. **“ProfilePic/93/ae316a8c-78e3-4427-9f6c-63a0d37d1d0d.jpg”**

**birthDate:** the birthDate property represents the user’s birth date and time. In the provided response, it is formatted as “yyyy-MM-ddTHH:mm:ss”, which indicates the date and time in ISO 8601 format, e.g. **“1999-08-02T00:00:00”**

**gender:** the gender property represents the user’s gender. The specific mapping of numeric values to genders may vary depending on the application or system’s implementation. Here, 0 is used for females, 1 for males, and 2 for unspecified, e.g. **1**

**isInitialized:** the isInitialized property is a Boolean value (true or false). It shows whether the user uses the app for the first time or not, e.g. **true**.

**token:** the token property typically represents an authentication token or access token associated with the user session. It is commonly used for subsequent API requests to authenticate and authorize the user.
