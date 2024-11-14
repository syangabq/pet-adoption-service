---
title: User
parent: API Reference
nav_order: 1
has_toc: false
---

# `user` resource

Base endpoint:

```shell
{base_url}/users
```

Contains information about users of the service.

To adopt a pet in the service, the user must first be added to the service. Learn more about the [pet resource](../pet/index.md).

## Resource properties

Sample `user` resource:

```js
{
    "id": 3,
    "first_name": "Amber",
    "last_name": "Cross",
    "email": "across@example.com",
    "phone": "456-333-8899",
    "interested_in": "cats"
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The user's unique record ID. |
| `first_name` | string | The user's first name. |
| `last_name` | string | The user's last name. |
| `email` | string | The user's email address. |
| `phone` | string | The user's phone number. |
| `interested_in` | string | The type of pet the user is interested in adopting. <br/> Can be one of: `cats`, `dogs`, `both` |
