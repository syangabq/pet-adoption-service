---
title: Enroll a new user
parent: Tutorials
nav_order: 1
---

# Tutorial: Enroll a new user

In this tutorial, you will enroll a new user in the Pet Adoption Service.

**Expected time to complete:** 15 minutes

## Before you begin

Make sure you have completed the [Get started](../get_started.md) quickstart on the development system that you will use for the tutorial.

## Enroll a new user

1. In a command-line tool, run the following command to start your local Pet Adoption Service, if it's not already running. Replace `<your-github-workspace>` with the directory that contains your clone of the `pet-adoption-service` repo.

    ```shell
    cd <your-github-workspace>/pet-adoption-service/api
    json-server -w pet-adoption-db-source.json
    ```

1. In another command-line window, run this command to make a `POST` request. In the request body, replace:

    * `<first_name>` with the new user's first name.
    * `<last_name>` with the new user's last name.
    * `<email>` with the new user's email address.
    * `<phone>` with the new user's phone number.
    * `<interested_in>` with the type of pet the new user is interested in adopting. This can be one of:
      * `cats`
      * `dogs`
      * `both`

    ```shell
    curl http://localhost:3000/users -X POST -H "Content-Type: application/json" -d '{
      "first_name": "<first_name>",
      "last_name": "<last_name>",
      "email": "<email>",
      "phone": "<phone>",
      "interested_in": "<interested_in>"
    }'
    ```

    For example, to enroll a new user named Martha Smith who is interested in adopting both cats and dogs, run:

    ```shell
    curl http://localhost:3000/users -X POST -H "Content-Type: application/json" -d '{
      "first_name": "Martha",
      "last_name": "Smith",
      "email": "msmith@example.com",
      "phone": "987-654-3210",
      "interested_in": "both"
    }'
    ```

1. The command returns the response body, which should include the new user's `id`, as well as the same property values that you used in the request body.

    If you ran the example command in the previous step to enroll Martha Smith, the response might look like:

    ```js
    {
      "first_name": "Martha",
      "last_name": "Smith",
      "email": "msmith@example.com",
      "phone": "987-654-3210",
      "interested_in": "both",
      "id": 5
    }
    ```

## What's next?

* After completing this tutorial using cURL, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.

* Try out other [tutorials](index.md) for the Pet Adoption Service or check out the [API Reference documentation](../api/index.md)!
