---
title: Pet
parent: API Reference
nav_order: 2
has_toc: false
---

# `pet` resource

Base endpoint:

```shell
{base_url}/pets
```

Contains information about pets in the service.

To adopt a pet in the service, the user must first be added to the service. Learn more about the [user resource](../user/index.md).

## Resource properties

Sample `pet` resource:

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
| `id` | number | The pet's unique record ID. |

## Supported operations

### GET

* [Get all pets](get_all_pets.md)
* [Get pet by ID](get_pet_by_id.md)

### POST

* [Add pet](add_pet.md)

### PATCH

* [Update pet's adoption status](update_pet_adoption_status.md)

### DELETE

* [Delete pet](delete_pet.md)
