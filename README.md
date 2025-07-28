# 📘 Blackboard Learn APIs – Postman Collection

---

## 📖 Table of Contents

- [📘 Blackboard Learn APIs – Postman Collection](#-blackboard-learn-apis--postman-collection)
  - [📖 Table of Contents](#-table-of-contents)
  - [🤓 Overview](#-overview)
  - [🛠️ Pre-requisites](#️-pre-requisites)
  - [🔐 Authentication Workflow](#-authentication-workflow)
  - [🚀 Using the Collection](#-using-the-collection)
  - [📦 Installation](#-installation)
  - [📚 Further Reading](#-further-reading)
  - [📄 Licence](#-licence)
  - [👤 Author](#-author)

---

## 🤓 Overview

A Postman collection for working with the Blackboard Learn REST APIs, as documented on [Anthology's Developer Portal](https://developer.blackboard.com/portal/displayApi). It includes endpoints for authentication, user and course management, content access, and more.

---

## 🛠️ Pre-requisites

Before using this collection, define the following **Global Variables** in Postman:

| Variable | Description |
| --- | --- |
| `baseUrl` | Your Blackboard Learn instance base URL (for example, `https://yourinstitution.learn.blackboard.com`) |
| `basicAuthUsername` | Your **Application Key** (Client ID), created in Anthology's [Developer Portal](https://developer.anthology.com/) following the instructions on [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication) |
| `basicAuthPassword` | Your **Application Secret** (Client Secret), paired with the Application Key |

These credentials are used to authenticate via Basic Auth and retrieve an OAuth 2.0 token.

---

## 🔐 Authentication Workflow

1. Send a `POST` request to:

   ```bash
   {{baseUrl}}/learn/api/public/v1/oauth2/token
   ```

2. Your `basicAuthUsername` and `basicAuthPassword` are sent via Basic Auth.

3. The response returns an `access_token`, which is saved in the `apiKey` environment variable.

4. This token is automatically used for future requests by setting the header:

   ```bash
   Authorization: Bearer {{apiKey}}
   ```

> ⚠️ Be sure to retrieve an access token before calling any other endpoints.

---

## 🚀 Using the Collection

- Endpoints are grouped by category (for example, Users, Courses, Enrolments).
- Some requests require specific parameters such as `userId` or `courseId`.
- Postman scripts are included to handle token storage and variable assignment.
- Supports chaining requests and managing dynamic workflows with variables and pre-request scripts.

---

## 📦 Installation

To install the collection:

```bash
git clone https://github.com/Karl-Horning/blackboard-learn-postman.git
cd blackboard-learn-postman
```

Then follow **Step 2: Import the Swagger File into Postman** in this guide:
👉 [Using Blackboard's Swagger File to Create a Postman Collection and Make an API Call](https://www.karlhorning.dev/dev-blog/posts/using-blackboards-swagger-file-to-create-a-postman-collection-and-make-an-api-call/)

---

## 📚 Further Reading

- 🔐 [Basic Authentication with REST](https://docs.anthology.com/docs/blackboard/rest-apis/getting-started/basic-authentication)
- 📘 [Blackboard Learn API Documentation](https://developer.blackboard.com/portal/displayApi)
- 🖥️ [Anthology Developer Portal](https://developer.anthology.com/)

---

## 📄 Licence

MIT © 2025 Karl Horning

---

## 👤 Author

Made with ❤️ by [Karl Horning](https://github.com/Karl-Horning)
