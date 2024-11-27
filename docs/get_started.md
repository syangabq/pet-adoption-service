---
title: Get started
nav_order: 2
has_toc: false
---

# Get started

In this quickstart, you will:

* Set up your development environment for testing the Pet Adoption Service locally.
* Start your local Pet Adoption Service.

**Estimated time to complete:** 20 minutes

## Set up your development environment

1. Install a current or long-term support (LTS) version of [Node.js](https://nodejs.org/en) on your development system.

1. Install a current version of [json-server](https://www.npmjs.com/package/json-server) on your development system.

1. [Create a GitHub account](https://github.com/join) if you do not already have one.

1. [Set up Git](https://docs.github.com/en/get-started/getting-started-with-git/set-up-git) on your development system.

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) the [`pet-adoption-service` repo](https://github.com/syangabq/pet-adoption-service).

## Start your local Pet Adoption Service

1. In a command-line tool, run the following command to start your local Pet Adoption Service. Replace `<your-github-workspace>` with the directory that contains your clone of the `pet-adoption-service` repo.

    ```shell
    cd <your-github-workspace>/pet-adoption-service/api
    json-server -w pet-adoption-db-source.json
    ```

    If your development environment is set up correctly, you should see the service start and display the URL of the service: `http://localhost:3000`.

1. In another command-line window, make a test call to the service.

    ```shell
    curl http://localhost:3000/users
    ```

1. If the service is running correctly, you should see a list of users returned from the service:

    ```js
    [
      {
        "first_name": "Sandy",
        "last_name": "Jones",
        "email": "sandyjones@example.com",
        "phone": "123-456-7890",
        "interested_in": "cats",
        "id": 1
      },
      {
        "first_name": "Todd",
        "last_name": "Edwards",
        "email": "t.edwards@example.com",
        "phone": "333-444-5555",
        "interested_in": "both",
        "id": 2
      },
      ...
    ]
    ```

## Troubleshooting

If you do not see the list of users, or receive an error at any step of the procedure, check that:

* You are in the correct directory.
* You typed the command correctly.
* All required software was installed correctly and is up-to-date.

## What's next?

Try out the [tutorials](tutorials/index.md) or check out the [API Reference documentation](api/index.md)!
