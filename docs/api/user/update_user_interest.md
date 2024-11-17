---
title: Update user's interest
parent: User
nav_order: 4
---

# Update user's interest

**PATCH** `/users/{id}`

Update the `interested_in` property of the [`user`](index.md) in the service with the specified `id`.

## URL

```shell
{base_url}/users/{id}
```

### Path parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `id` | number | The `id` of the [`user`](index.md#resource-properties) to update. |

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
| `interested_in` | string | The type of pet the user is interested in adopting. <br/> Can be one of: `cats`, `dogs`, `both` |

#### Example request body

```js
{
  "interested_in": "both"
}
```

## Response

### Response body

* Returns the [`user`](index.md) object if it was successfully updated.
* Returns an empty JSON object if no users in the service have the specified `id`.
* Returns an error if there was an issue with the request.

#### Example response body

```js
{
  "first_name": "Fiona",
  "last_name": "Burns",
  "email": "fionab@example.com",
  "phone": "222-333-4455",
  "interested_in": "both",
  "id": 4
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested user was successfully updated. |
| 400 | Bad Request | The request was invalid. Check if the request body is valid JSON that matches the [expected request body](#request-body). |
| 404 | Not Found | The requested user was not found in the service. Check if the [`id` parameter](#path-parameters) in the URL path is correct. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
