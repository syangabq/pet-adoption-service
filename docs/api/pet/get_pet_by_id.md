---
title: Get pet by ID
parent: Pet
nav_order: 2
---

# Get pet by ID

GET
{: .label .label-blue .ml-0 }
`/pets/{id}`
{: .d-inline-block }

Get the [`pet`](index.md) in the service with the specified `id`.

## URL

```shell
{base_url}/pets/{id}
```

### Path parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `id` | number | The `id` of the [`pet`](index.md#resource-properties) to return. |

### Query parameters

None

## Request

### Request headers

None

### Request body

None

## Response

### Response body

* Returns the [`pet`](index.md) object if the pet with the specified `id` exists in the service.
* Returns an empty JSON object if no pets in the service have the specified `id`.

#### Example response body

```js
{
  "name": "Fred",
  "type": "dog",
  "breed": "Poodle",
  "age": 24,
  "color": "brown",
  "personality": "friendly",
  "status": "available",
  "user_id": null,
  "id": 4
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested pet was successfully returned. |
| 404 | Not Found | The requested pet was not found in the service. Check if the [`id` parameter](#path-parameters) in the URL path is correct. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
