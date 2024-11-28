---
title: Search for users
parent: Tutorials
nav_order: 3
---

# Tutorial: Search for users

In this tutorial, you will search for users in the Pet Adoption Service.

**Expected time to complete:** 15 minutes

## Before you begin

Make sure you have completed the [Get started](../get_started.md) quickstart on the development system that you will use for the tutorial.

## Search for users

1. In a command-line tool, [start your local Pet Adoption Service](../get_started.md#start-your-local-pet-adoption-service), if it is not already running.

1. In another command-line window, run this command to make a `GET` request to list all users enrolled in the service.

    ```shell
    curl http://localhost:3000/users
    ```

    You may add any combination of the [supported query params](../api/user/get_all_users.md#query-parameters) to the URL to filter your search.

    ```shell
    curl "http://localhost:3000/users?<param_1_name>=<param_1_value>&<param_2_name>=<param_2_value>"
    ```

    For example, to find all users who are interested in adopting dogs, run:

    ```shell
    curl "http://localhost:3000/users?interested_in=dogs"
    ```

1. The command returns the response body, which should include the list of users filtered by the constraints specified in the query params of the request URL.

    If you ran the example command in the previous step to find all users who are interested in adopting dogs, the response might look like:

    ```js
    [
      {
        "first_name": "Fiona",
        "last_name": "Burns",
        "email": "fionab@example.com",
        "phone": "222-333-4455",
        "interested_in": "dogs",
        "id": 4
      }
    ]
    ```

## What's next?

* After completing this tutorial using cURL, you might like to repeat it in
your favorite programming language. To do this, adapt the values from
the tutorial to the properties and arguments that the language uses to
make REST API calls.

* Try out other [tutorials](index.md) for the Pet Adoption Service or check out the [API Reference documentation](../api/index.md)!
