---
title: Add a new pet
parent: Tutorials
nav_order: 2
---

# Tutorial: Add a new pet

In this tutorial, you will add a new pet to the Pet Adoption Service.

**Expected time to complete:** 15 minutes

## Before you begin

Make sure you have completed the [Get started](../get_started.md) quickstart on the development system that you will use for the tutorial.

## Add a new pet

1. In a command-line tool, run the following command to start your local Pet Adoption Service, if it's not already running. Replace `<your-github-workspace>` with the directory that contains your clone of the `pet-adoption-service` repo.

    ```shell
    cd <your-github-workspace>/pet-adoption-service/api
    json-server -w pet-adoption-db-source.json
    ```

1. In another command-line window, run this command to make a `POST` request. In the request body, replace:

    * `<name>` with the new pet's name.
    * `<type>` with the type of the new pet. This can be one of:
      * `cat`
      * `dog`
    * `<breed>` with the pet's breed.
    * `<age>` with the pet's age in months.
    * `<color>` with the pet's color.
    * `<personality>` with a description of the pet's personality.
    * `<status>` with the pet's adoption status. This can be one of:
      * `adopted`
      * `available`
    * `<user_id>` with the `id` property of the [`user`](../api/user/index.md#resource-properties) resource representing the user that adopted this pet, or `null` if the pet is available for adoption.

    ```shell
    curl http://localhost:3000/pets -X POST -H "Content-Type: application/json" -d '{
      "name": "<name>",
      "type": "<type>",
      "breed": "<breed>",
      "age": <age>,
      "color": "<color>",
      "personality": "<personality>",
      "status": "<status>",
      "user_id": <user_id>
    }'
    ```

    For example, to add a new pug named Daisy Duck that is available for adoption, run:

    ```shell
    curl http://localhost:3000/pets -X POST -H "Content-Type: application/json" -d '{
      "name": "Daisy Duck",
      "type": "dog",
      "breed": "Pug",
      "age": 18,
      "color": "fawn",
      "personality": "playful",
      "status": "available",
      "user_id": null
    }'
    ```

1. The command returns the response body, which should include the new pet's `id`, as well as the same property values that you used in the request body.

    If you ran the example command in the previous step to add Daisy Duck, the response might look like:

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

## What's next?

* After completing this tutorial using cURL, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.

* Try out other [tutorials](index.md) for the Pet Adoption Service or check out the [API Reference documentation](../api/index.md)!
