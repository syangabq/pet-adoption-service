---
title: Search for pets
parent: Tutorials
nav_order: 4
---

# Tutorial: Search for pets

In this tutorial, you will search for pets in the Pet Adoption Service.

**Expected time to complete:** 15 minutes

## Before you begin

Make sure you have completed the [Get started](../get_started.md) quickstart on the development system that you will use for the tutorial.

## Search for pets

1. In a command-line tool, [start your local Pet Adoption Service](../get_started.md#start-your-local-pet-adoption-service), if it is not already running.

1. In another command-line window, run this command to make a `GET` request to list all users enrolled in the service.

    ```shell
    curl http://localhost:3000/pets
    ```

    You may add any combination of the [supported query params](../api/pet/get_all_pets.md#query-parameters) to the URL to filter your search.

    ```shell
    curl "http://localhost:3000/pets?<param_1_name>=<param_1_value>&<param_2_name>=<param_2_value>"
    ```

    For example, to find all Domestic shorthairs that are 2 years old or younger, run:

    ```shell
    curl "http://localhost:3000/pets?breed=Domestic%20shorthair&age_lte=24"
    ```

1. The command returns the response body, which should include the list of pets filtered by the constraints specified in the query params of the request URL.

    If you ran the example command in the previous step to find all Domestic shorthairs that are 2 years old or younger, the response might look like:

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
      }
    ]
    ```

## What's next?

* After completing this tutorial using cURL, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.

* Try out other [tutorials](index.md) for the Pet Adoption Service or check out the [API Reference documentation](../api/index.md)!
