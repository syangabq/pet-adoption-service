---
title: Update pet's adoption status
parent: Pet
nav_order: 4
---

# Update pet's adoption status

**PATCH** `/pets/{id}`

Update the adoption status of the [`pet`](index.md) in the service with the specified `id`.

## URL

```shell
{base_url}/pets/{id}
```

### Path parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `id` | number | The `id` of the [`pet`](index.md#resource-properties) to update. |

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
| `status` | string | The pet's adoption status. <br/> Can be one of: `adopted`, `available` |
| `user_id` | number \| null | The `id` property of the [`user`](../user/index.md) resource representing the user that adopted this pet, or `null` if the pet is available for adoption. |

#### Example request body

```js
{
  "status": "adopted",
  "user_id": 2
}
```

## Response

### Response body

* Returns the [`pet`](index.md) object if it was successfully updated.
* Returns an empty JSON object if no pets in the service have the specified `id`.
* Returns an error if there was an issue with the request.

#### Example response body

```js
{
  "name": "Fred",
  "type": "dog",
  "breed": "Poodle",
  "age": 24,
  "color": "brown",
  "personality": "friendly",
  "status": "adopted",
  "user_id": 2,
  "id": 4
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested pet was successfully updated. |
| 400 | Bad Request | The request was invalid. Check if the request body is valid JSON that matches the [expected request body](#request-body). |
| 404 | Not Found | The requested pet was not found in the service. Check if the [`id` parameter](#path-parameters) in the URL path is correct. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
