---
title: Pet
nav_order: 3
---

# `pet` resource

Base endpoint:

```shell
{base_url}/pets
```

Contains information about pets in the service.

To adopt a pet in the service, the user must first be added to the service. Learn more about the [user resource](user.md).

## Resource properties

Sample `pet` resource:

```js
{
    "id": 4,
    "name": "Fred",
    "type": "dog",
    "breed": "Poodle",
    "age": 24,
    "color": "brown",
    "personality": "friendly",
    "status": "available",
    "user_id": null
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The pet's unique record ID. |
| `name` | string | The pet's name. |
| `type` | string | The type of pet. <br/> Can be one of: `cat`, `dog` |
| `breed` | string | The pet's breed. |
| `age` | number | The pet's age in months. The service will automatically update the value of this property every month. |
| `color` | string | The pet's color. |
| `personality` | string | Description of the pet's personality. |
| `status` | string | The pet's adoption status. <br/> Can be one of: `adopted`, `available` |
| `user_id` | string \| null | The ID of the user resource representing the user that adopted this pet, or `null` if the pet has not been adopted yet. |
