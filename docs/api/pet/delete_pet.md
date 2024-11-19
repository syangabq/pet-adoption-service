---
title: Delete pet
parent: Pet
nav_order: 5
---

# Delete pet

**DELETE** `/pets/{id}`

Delete the [`pet`](index.md) in the service with the specified `id`.

## URL

```shell
{base_url}/pets/{id}
```

### Path parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `id` | number | The `id` of the [`pet`](index.md#resource-properties) to delete. |

### Query parameters

None

## Request

### Request headers

None

### Request body

None

## Response

### Response body

Returns an empty JSON object.

#### Example response body

```js
{}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested pet was successfully deleted from the service. |
| 404 | Not Found | The requested pet was not found in the service. Check if the [`id` parameter](#path-parameters) in the URL path is correct. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
