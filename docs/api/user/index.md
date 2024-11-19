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
  "first_name": "Amber",
  "last_name": "Cross",
  "email": "across@example.com",
  "phone": "456-333-8899",
  "interested_in": "cats",
  "id": 3
}
```

| Property name | Type | Description |
| ------------- | ---- | ----------- |
| `first_name` | string | The user's first name. |
| `last_name` | string | The user's last name. |
| `email` | string | The user's email address. |
| `phone` | string | The user's phone number. |
| `interested_in` | string | The type of pet the user is interested in adopting. <br/> Can be one of: `cats`, `dogs`, `both` |
| `id` | number | The user's unique record ID. |

## Supported operations

### GET

* [Get all users](get_all_users.md)
* [Get user by ID](get_user_by_id.md)

### POST

* [Enroll user](enroll_user.md)

### PATCH

* [Update user's interest](update_user_interest.md)

### DELETE

* [Delete user](delete_user.md)
