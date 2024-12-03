---
title: Update pet properties
parent: Pet
nav_order: 4
---

# Update pet properties

PATCH
{: .label .label-purple .ml-0 }
`/pets/{id}`
{: .d-inline-block }

Update the properties of the [`pet`](index.md) in the service with the specified `id`.

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

Provide a JSON object with the properties to update, and their new values. Any of the following properties may be updated:

| Property name | Type | Description |
| ------------- | ---- | ----------- |
| `name` | string | The pet's name. |
| `type` | string | The type of pet. <br/> Can be one of: `cat`, `dog` |
| `breed` | string | The pet's breed. |
| `age` | number | The pet's age in months. The service will automatically update the value of this property every month. |
| `color` | string | The pet's color. |
| `personality` | string | Description of the pet's personality. |
| `status` | string | The pet's adoption status. <br/> Can be one of: `adopted`, `available` |
| `user_id` | number \| null | The `id` property of the [`user`](../user/index.md#resource-properties) resource representing the user that adopted this pet, or `null` if the pet is available for adoption. |

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
