---
title: App Center API Documentation
description: Explore the App Center API with Swagger
keywords: swagger
author: amchew
ms.author: amchew
ms.date: 01/24/2019
ms.topic: article
ms.assetid: ec67a6fc-6923-4a33-b655-f6d3308dca64
ms.service: vs-appcenter
ms.custom: api
---

# API Documentation

Explore the App Center API Service with [swagger](https://openapi.appcenter.ms).

## <a name="section1"/>Acquiring an App Center API token

Each API request must include an API token from your App Center account; to obtain a token:

1. Navigate to [https://appcenter.ms](https://appcenter.ms) and login using your account credentials.
2. On the top right corner of the App Center portal, click your account avatar, then select **Account Settings**.
3. In the middle panel, select **API Tokens** from the menu list.
4. On the top right corner, click **New API token**.
5. In the text field, enter a descriptive name for your token.
6. Select the type of access for your API token:

   **Full Access:** A full access API token has all the permissions that the associated user has for that app. For example, if the user does not have manager or developer permissions for an app, the user cannot run a test (which requires developer or manager permissions) even though the user is using a full access API token.

   **Read Only:** A read only API token has viewer access permissions. For example, with a read only API token, the user can perform actions such as reading data from crashes, analytics, and getting basic app information. Users cannot perform actions such as changing the app settings, triggering a build, creating an export configuration etc.

7. At the bottom of the panel, click **Add new API token**.
8. This will generate a pop up with your API token. Copy and store it in a secure location for later use. For security reasons, you will not be able to see or generate the same token again after you click the **Close** button.
9. Click the **Close** button.

Store the token somewhere as you'll need it when working with the App Center Swagger and when sending API requests from an application to App Center.

## Using an API Token in an API request

When sending API requests to App Center from an application, you must include the API token in the header of every request sent to App Center. Pass the API token in the request's `X-API-Token` header property.

## <a name="section3"/>Using an API Token with the App Center Swagger

The [App Center Swagger](https://openapi.appcenter.ms/) handles API authentication for you, so you don't have to worry about pasting the API token into all of your requests. To configure Swagger with your API token, complete the following steps:

1. Navigate to App Center's [swagger](https://openapi.appcenter.ms) page to explore our APIs.
2. On the upper right corner, click on the **Authorize** button.
3. Under the **APIToken** section, paste the API token value that you just copied into the text field titled **Value** and click **Authorize**.

    ![Setting api token value to authorize our API's](~/api-docs/images/authorization_withtoken.PNG)

4. If it shows "Authorized" and a Logout-Button, authorization was successful. On the top right corner of the pop up, click the "X" to exit the pop up.
5. You are now able to use any App Center API and see the response. Enjoy!

## Making your first API call through swagger

This section shows you how to use App Center's [swagger page](https://openapi.appcenter.ms) by using the API call `GET /v0.1/user`. This API call returns the user's profile data.

1. Create an API token by following the instructions in the [first section](#section1).
2. Authorize the swagger to use your API token following the instructions in the [previous section](#section3).
3. Navigate to App Center's [swagger](https://openapi.appcenter.ms) page to explore our APIs.
4. Under **Account**, click on `GET /v0.1/user`.
5. On the left-hand corner, click the **Try it out** button.
6. Click the **Execute** button under the **Parameters** section.
7. Awesome! You can now see the response under the **Responses** section.

## Find your App Center app name and owner name

Some of App Center's API and CLI require an app name and owner name as parameters. An example is the API call to remove the user from the app, [`DELETE /v0.1/apps/{owner_name}/{app_name}/users/{user_email}`](https://openapi.appcenter.ms/#/account/apps_removeUser).

You can find the app name and owner name from your App Center app URL, or using the [App Center CLI](https://github.com/Microsoft/appcenter-cli).

### From App Center app URL

1. Navigate to [https://appcenter.ms](https://appcenter.ms).
2. Navigate to your app.
3. When you look at your app's URL, it is in the format `https://appcenter.ms/users/{owner-name}/apps/{app-name}`.

Owner can be a user or an organization. For example,

| Owner| URL                                                       | Owner name     | App name   |
| -----| --------------------------------------------------------- | -------------- | ---------- |
| User | `https://appcenter.ms/users/joedeveloper/apps/DiceOut-01` | joedeveloper   | DiceOut-01 |
| Org  | `https://appcenter.ms/orgs/CrystalGeyser/apps/MacOS-app`  | CrystalGeyser  | MacOS-app  |

### From App Center CLI

The App Center CLI requires Node.js version 8 or higher.

1. Open a terminal window or command prompt
2. Execute the following command:

    ```shell
    npm install -g appcenter-cli
    ```
3. After completing the CLI installation, execute the following command:

    ```shell
    appcenter apps list
    ```

    App Center displays a list of apps with the format `{owner-name}`/`{app-name}`.

Refer to [App Center CLI](https://github.com/Microsoft/appcenter-cli) for the full documentation and list of commands.
