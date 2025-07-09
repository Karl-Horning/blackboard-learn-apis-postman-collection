# 📘 Blackboard Learn APIs – Postman Collection

This Postman collection provides access to the Blackboard Learn REST APIs, using endpoints documented at [Anthology's Developer Portal](https://developer.blackboard.com/portal/displayApi). It supports authentication, user/course management, content access, and other tasks.

## 🛠️ Pre-requisites

Before using this collection, define the following **Global Variables** in Postman:

| Variable | Description |
| --- | --- |
| `baseUrl` | Your Blackboard Learn instance base URL (for example, `https://yourinstitution.learn.blackboard.com`) |
| `basicAuthUsername` | Your **Application Key** (Client ID), created in Anthology's [Developer Portal](https://developer.anthology.com/) following the instructions on [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication) |
| `basicAuthPassword` | Your **Application Secret** (Client Secret), paired with the Application Key |

These credentials are used to authenticate using Basic Auth and retrieve an OAuth 2.0 token.

## 🔐 Authentication Workflow

To authenticate:

1. Send a `POST` request to:
   `{{baseUrl}}/learn/api/public/v1/oauth2/token`

2. This sends your `basicAuthUsername` and `basicAuthPassword` via Basic Auth.

3. The response returns an `access_token`, which is stored in the `apiKey` environment variable.

4. The token is then automatically applied to future requests using the header:
   `Authorization: Bearer {{apiKey}}`

> ⚠️ Always send the OAuth token request before accessing other endpoints.

## 🚀 Using the Collection

- Endpoints are grouped by category: Users, Courses, Enrolments, etc.
- Some requests require specific IDs (userId, courseId, etc.).
- Postman scripts are used to manage environment variables and tokens efficiently.
- This workspace supports chaining requests and dynamic workflows using variables and scripts.

## 📚 Further Reading

- 🔐 [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication)
- 📘 [Blackboard Learn API Documentation](https://developer.blackboard.com/portal/displayApi)
- 🖥️ [Anthology Developer Portal](https://developer.anthology.com/)
