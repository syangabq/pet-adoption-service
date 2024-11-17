---
title: Get all users
parent: User
nav_order: 1
---

# Get all users

**GET** `/users`

Get all [`users`](index.md) that have been enrolled in the service.

## URL

```shell
{base_url}/users
```

### Path parameters

None

### Query parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `first_name` | string | Return users with the given first name. |
| `last_name` | string | Return users with the given last name. |
| `email` | string | Return users with the given email. |
| `phone` | string | Return users with the given phone number. |
| `interested_in` | string | Return users with the given type of pet the user is interested in adopting. <br/> Can be one of: `cats`, `dogs`, `both` |

## Request

### Request headers

None

### Request body

None

## Response

### Response body

Returns an array of [`user`](index.md) objects.

#### Example response body

```js
[
  {
    "first_name": "Sandy",
    "last_name": "Jones",
    "email": "sandyjones@example.com",
    "phone": "123-456-7890",
    "interested_in": "cats",
    "id": 1
  },
  {
    "first_name": "Todd",
    "last_name": "Edwards",
    "email": "t.edwards@example.com",
    "phone": "333-444-5555",
    "interested_in": "both",
    "id": 2
  },
  ...
]
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested users in the service were successfully returned. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
