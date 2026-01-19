---
description: >-
  Labor markets are diverse and fast changing, so a useful taxonomy must be
  localizable and adaptable in a transparent way. Learn more about the API that
  powers our open taxonomy platform.
---

# Open Taxonomy Platform API

## Overview and Format

The [Open Taxonomy Platform](./) API provides secure access to taxonomy models, occupations, skills, and their respective groups, enabling seamless integration with your applications. The base URL for all API requests is [https://taxonomy.tabiya.tech/taxonomy/api-doc/swagger/](https://taxonomy.tabiya.tech/api-doc/swagger/). To ensure standardized communication, all requests and responses (except file uploads) utilize the JSON format, making it straightforward to integrate with any modern programming environment.

## Credentials and Authentication

#### Prerequisites

Before you can integrate with the APIs, you must obtain credentials from the platform administrators. **Request credentials** via the dedicated email address on this [page](https://docs.tabiya.org/#discover-tabiyas-work). Depending on the authentication method you choose, you will receive:&#x20;

* **API Keys**: A unique `X-API-Key`&#x20;
* **M2M OAuth:** An `Authorization server URL`, `Client ID`, and `Client Secret`

#### API Path Prefixes

All partner APIs use the following path prefix:

* `/api/partner`  for API Keys
* `/api/app`  For JWT Tokens received via M2M OAuth.

#### Authentication Methods

We support two authentication methods. Choose the one that aligns with your security requirements.

#### API Keys

API Keys provide a simple authentication mechanism suitable for basic integrations.

**Usage**

Include the API key in every request using the `X-API-Key` HTTP header.

**Example:-**

```bash
curl -X GET \
  https://taxonomy.tabiya.tech/api/partner/info \
  -H "X-API-Key: YOUR_API_KEY"
```

#### Machine to Machine (M2M) OAuth 2.0

Machine to Machine OAuth 2.0 is the recommended method for secure, automated service-to-service communication using short-lived access tokens

**Step 1**

Send an HTTP `POST` request to the **Authorization server URL** using the `Client ID` and `Client Secret`.

**Example**

```bash
curl -X POST YOUR_AUTHORIZATION_SERVER_URL \
     -H "Content-Type: application/x-www-form-urlencoded" \
     -d "grant_type=client_credentials&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET"
```

The authorization server responds with an access token:

```json
{
   "access_token": "YOUR_ACCESS_TOKEN",
   "token_type": "Bearer",
   "expires_in": 3600
}
```

For more information refer to the Auth token documentation on the part of exchanging client credentials for [access token](https://oauth.net/2/access-tokens/).

* [https://docs.aws.amazon.com/cognito/latest/developerguide/token-endpoint.html#post-token-positive-exchanging-client-credentials-for-an-access-token-in-request-body](https://docs.aws.amazon.com/cognito/latest/developerguide/token-endpoint.html#post-token-positive-exchanging-client-credentials-for-an-access-token-in-request-body)



**Step 2**

Send a request to the API with the access token from the previous result.

```bash
curl -X GET \
   https://taxonomy.tabiya.tech/api/app/info \
   -H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

For more details, see the [Scopes, M2M, and resource servers](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-define-resource-servers.html) documentation on AWS.



## Direct Access to the OpenAPI Specification

Two access methods are available for the API specifications. The primary method is through the interactive Swagger UI documentation, which allows browsing and live testing of all endpoints. Crucially, for developers looking to quickly configure their clients, a direct, standalone link to the OpenAPI v3 JSON specification file is provided. This link is essential for developers who want to import the entire API definition into tools like Postman or Insomnia (using the _Import > Link option_), accelerating setup by automatically generating all endpoint, parameter, and schema definitions:

* OpenAPI Specification link: [https://taxonomy.tabiya.tech/api-doc/swagger/tabiya-api.json](https://taxonomy.tabiya.tech/api-doc/swagger/tabiya-api.json)
* Swagger UI link: [https://taxonomy.tabiya.tech/api-doc/swagger/](https://taxonomy.tabiya.tech/api-doc/swagger/)
* ReDoc UI link: [https://taxonomy.tabiya.tech/api-doc/redoc/](https://taxonomy.tabiya.tech/api-doc/redoc/)

