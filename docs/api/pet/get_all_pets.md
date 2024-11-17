---
title: Get all pets
parent: Pet
nav_order: 1
---

# Get all pets

**GET** `/pets`

Get all [`pets`](index.md) that have been added to the service.

## URL

```shell
{base_url}/pets
```

### Path parameters

None

### Query parameters

| Parameter name | Type | Description |
| -------------- | ---- | ----------- |
| `name` | string | Return pets with the given name. |
| `name_like` | RegExp | Return pets with a name that matches the given regular expression. |
| `type` | string | Return pets with the given type. <br/> Can be one of: `cat`, `dog` |
| `type_like` | RegExp | Return pets with a type that matches the given regular expression. |
| `breed` | string | Return pets with the given breed. |
| `breed_like` | RegExp | Return pets with a breed that matches the given regular expression. |
| `age` | number | Return pets with the given age in months. |
| `age_gte` | number | Return pets with an age greater than or equal to the given age in months. |
| `age_lte` | number | Return pets with an age less than or equal to the given age in months. |
| `color` | string | Return pets with the given color. |
| `color_like` | RegExp | Return pets with a color that matches the given regular expression. |
| `personality` | string | Return pets with the given personality. |
| `personality_like` | RegExp | Return pets with a personality that matches the given regular expression. |
| `status` | string | Return pets with the given adoption status. <br/> Can be one of: `adopted`, `available` |
| `status_like` | RegExp | Return pets with a status that matches the given regular expression. |
| `user_id` | number | Return pets who have been adopted by the [`user`](../user/index.md) with the given ID. |

## Request

### Request headers

None

### Request body

None

## Response

### Response body

Returns an array of [`pet`](index.md) objects.

#### Example response body

```js
[
  {
    "name": "Cheetah",
    "type": "cat",
    "breed": "Domestic shorthair",
    "age": 24,
    "color": "orange",
    "personality": "mellow",
    "status": "adopted",
    "user_id": 1,
    "id": 1
  },
  {
    "name": "Rufus",
    "type": "dog",
    "breed": "Husky",
    "age": 6,
    "color": "grey",
    "personality": "friendly",
    "status": "available",
    "user_id": null,
    "id": 2
  },
  ...
]
```

### Response status

| Status code | Response status | Description |
| ----------- | --------------- | ----------- |
| 200 | OK | The requested pets in the service were successfully returned. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
