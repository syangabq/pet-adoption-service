---
title: Enroll user
parent: User
nav_order: 3
---

# Enroll user

POST
{: .label .label-green .ml-0 }
`/users`
{: .d-inline-block }

Enroll a [`user`](index.md) in the service.

## URL

```shell
{base_url}/users
```

### Path parameters

None

### Query parameters

None

## Request

### Request headers

| Header name | Value |
| ----------- | ----- |
| `Content-Type` | `application/json` |

### Request body

Provide a JSON object with the following properties:

| Property name | Type | Description |
| ------------- | ---- | ----------- |
| `first_name` | string | The user's first name. |
| `last_name` | string | The user's last name. |
| `email` | string | The user's email address. |
| `phone` | string | The user's phone number. |
| `interested_in` | string | The type of pet the user is interested in adopting. <br/> Can be one of: `cats`, `dogs`, `both` |

#### Example request body

```js
{
  "first_name": "Martha",
  "last_name": "Smith",
  "email": "msmith@example.com",
  "phone": "987-654-3210",
  "interested_in": "both"
}
```

## Response

### Response body

* Returns the [`user`](index.md) object if it was successfully enrolled in the service.
* Returns an error if there was an issue with the request.

#### Example response body

```js
{
  "first_name": "Martha",
  "last_name": "Smith",
  "email": "msmith@example.com",
  "phone": "987-654-3210",
  "interested_in": "both",
  "id": 5
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 201 | Created | The requested user was successfully enrolled in the service. |
| 400 | Bad Request | The request was invalid. Check if the request body is valid JSON that matches the [expected request body](#request-body). |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
