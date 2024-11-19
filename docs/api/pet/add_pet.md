---
title: Add pet
parent: Pet
nav_order: 3
---

# Add pet

**POST** `/pets`

Add a [`pet`](index.md) to the service.

## URL

```shell
{base_url}/pets
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
  "name": "Daisy Duck",
  "type": "dog",
  "breed": "Pug",
  "age": 18,
  "color": "fawn",
  "personality": "playful",
  "status": "available",
  "user_id": null
}
```

## Response

### Response body

* Returns the [`pet`](index.md) object if it was successfully added to the service.
* Returns an error if there was an issue with the request.

#### Example response body

```js
{
  "name": "Daisy Duck",
  "type": "dog",
  "breed": "Pug",
  "age": 18,
  "color": "fawn",
  "personality": "playful",
  "status": "available",
  "user_id": null,
  "id": 5
}
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 201 | Created | The requested pet was successfully added to the service. |
| 400 | Bad Request | The request was invalid. Check if the request body is valid JSON that matches the [expected request body](#request-body). |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
