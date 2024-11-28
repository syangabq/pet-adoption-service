---
title: Update a pet's adoption status
parent: Tutorials
nav_order: 5
---

# Tutorial: Update a pet's adoption status

In this tutorial, you will update the adoption status of a pet in the Pet Adoption Service.

**Expected time to complete:** 15 minutes

## Before you begin

* Make sure you have completed the [Get started](../get_started.md) quickstart on the development system that you will use for the tutorial.

* Make sure that a pet already exists in the service or add a new pet as described in the [Add a new pet tutorial](add_a_new_pet.md). You'll need the `id` of the [`pet`](../api/pet/index.md#resource-properties) resource that you want to change.

## Update a pet's adoption status

1. In a command-line tool, [start your local Pet Adoption Service](../get_started.md#start-your-local-pet-adoption-service), if it is not already running.

1. In another command-line window, run this command to make a `PATCH` request. In the request body, replace:

    * `<id>` with the `id` of the pet that you want to change.
    * `<status>` with the pet's new adoption status. This can be one of:
      * `adopted`
      * `available`
    * `<user_id>` with the `id` property of the [`user`](../api/user/index.md#resource-properties) resource representing the user that adopted this pet, or `null` if the pet is now available for adoption.

    ```shell
    curl http://localhost:3000/pets/<id> -X PATCH -H "Content-Type: application/json" -d '{
      "status": "<status>",
      "user_id": <user_id>
    }'
    ```

    For example, if the pet with an `id` of `4` was newly adopted by the user with an `id` of `2`, run:

    ```shell
    curl http://localhost:3000/pets/4 -X PATCH -H "Content-Type: application/json" -d '{
      "status": "adopted",
      "user_id": 2
    }'
    ```

1. The command returns the response body, which should include the same `id` as the pet you changed, as well as the updated `status` and `user_id` values.

    If you ran the example command in the previous step to update pet `4` to be adopted by user `2`, the response might look like:

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

## What's next?

* After completing this tutorial using cURL, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.

* Try out other [tutorials](index.md) for the Pet Adoption Service or check out the [API Reference documentation](../api/index.md)!
