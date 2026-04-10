# Blackboard Learn APIs – Postman Collection

> This project is no longer maintained. It is preserved here for reference only.

A Postman collection for the Blackboard Learn REST APIs, built as part of a comparison of REST APIs across three LMS platforms (Blackboard, Canvas, and Brightspace). It covers authentication, user and course management, and content access.

## Prerequisites

Before using this collection, define the following **Global Variables** in Postman:

| Variable | Description |
| --- | --- |
| `baseUrl` | Your Blackboard Learn instance base URL (for example, `https://yourinstitution.learn.blackboard.com`) |
| `basicAuthUsername` | Your **Application Key** (Client ID), created in Anthology's [Developer Portal](https://developer.anthology.com/) following the instructions on [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication) |
| `basicAuthPassword` | Your **Application Secret** (Client Secret), paired with the Application Key |

These credentials are used to authenticate via Basic Auth and retrieve an OAuth 2.0 token.

## Authentication workflow

1. Send a `POST` request to:

   ```text
   {{baseUrl}}/learn/api/public/v1/oauth2/token
   ```

2. Your `basicAuthUsername` and `basicAuthPassword` are sent via Basic Auth.

3. The response returns an `access_token`, which is saved in the `apiKey` environment variable.

4. This token is automatically used for future requests by setting the header:

   ```text
   Authorization: Bearer {{apiKey}}
   ```

> ⚠️ Be sure to retrieve an access token before calling any other endpoints.

## Using the collection

- Endpoints are grouped by category (for example, Users, Courses, Enrolments).
- Some requests require specific parameters such as `userId` or `courseId`.
- Postman scripts are included to handle token storage and variable assignment.
- Requests can be chained using variables and pre-request scripts.

## Setup

To import the collection:

```text
git clone https://github.com/Karl-Horning/blackboard-learn-apis-postman-collection.git
```

Then import `src/postman-collection/Learn APIs.postman_collection.json` into Postman via **File > Import**.

## Further reading

- [Testing LMS APIs: What an OpenAPI Spec Gives You (and What It Doesn't)](https://www.karlhorning.dev/blog/testing-lms-apis)
- [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication)
- [Blackboard Learn API Documentation](https://developer.blackboard.com/portal/displayApi)
- [Anthology Developer Portal](https://developer.anthology.com/)

## Issues

If you have questions, open a [GitHub issue](https://github.com/Karl-Horning/blackboard-learn-apis-postman-collection/issues).

## Licence

MIT © 2025 [Karl Horning](https://github.com/Karl-Horning)
