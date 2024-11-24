---
title: Get user by ID
parent: User
nav_order: 2
---

# Get user by ID

GET
{: .label .label-blue .ml-0 }
`/users/{id}`
{: .d-inline-block }

Get the [`user`](index.md) in the service with the specified `id`.

## URL

```shell
{base_url}/users/{id}
```

### Path parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `id` | number | The `id` of the [`user`](index.md#resource-properties) to return. |

### Query parameters

None

## Request

### Request headers

None

### Request body

None

## Response

### Response body

* Returns the [`user`](index.md) object if the user with the specified `id` exists in the service.
* Returns an empty JSON object if no users in the service have the specified `id`.

#### Example response body

```js
{
  "first_name": "Fiona",
  "last_name": "Burns",
  "email": "fionab@example.com",
  "phone": "222-333-4455",
  "interested_in": "dogs",
  "id": 4
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested user was successfully returned. |
| 404 | Not Found | The requested user was not found in the service. Check if the [`id` parameter](#path-parameters) in the URL path is correct. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
