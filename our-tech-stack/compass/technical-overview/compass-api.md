---
description: >-
  Compass is an innovative, AI-powered chatbot designed to revolutionize the way
  a young person identifies, articulates, and showcases their skills. Learn more
  about the API that powers Compass.
---

# Compass API

## Overview and Format

The [Compass](../) API provides secure access to users' preferences, conversation state, and experiences and skills, enabling seamless integration with your applications. The base URL for all API requests is [https://demo.compass.tabiya.tech/api/docs](https://demo.compass.tabiya.tech/api/docs). To ensure standardized communication, all requests and responses (except file uploads) utilize the JSON format, making it straightforward to integrate with any modern programming environment.

## Credentials and Authentication

Before integration, developers must obtain the necessary credentials.&#x20;

* API Keys: An API Key, can be requested by contacting the admins via the designated email. Once issued, the API key must be included in the x-api-key header of every request. For example, the header should be formatted as: x-api-key: \<your-access-token>.
* Authorization Headers: These are compass user-specific and require first logging in via the compass app to obtain the access token.

## Direct Access to the OpenAPI Specification

Two access methods are available for the API specifications. The primary method is through the interactive Swagger UI documentation page, which allows browsing and live testing of all endpoints. Crucially, for developers looking to quickly configure their clients, a direct, standalone link to the OpenAPI v3 JSON specification file is provided. This link is essential for developers who want to import the entire API definition into tools like Postman or Insomnia (using the _Import > Link option_), accelerating setup by automatically generating all endpoint, parameter, and schema definitions:

*  OpenAPI Specification link: [https://demo.compass.tabiya.tech/openapi.json](https://demo.compass.tabiya.tech/openapi.json)
* Swagger link: [https://demo.compass.tabiya.tech/api/docs](https://demo.compass.tabiya.tech/api/docs)

## Usage Policies and Rate Limiting

To ensure fair and stable access for all users, we enforce a Rate Limiting policy. Developers are limited to 120 requests per minute per unique API key. Exceeding this threshold will immediately result in an HTTP 429 "Too Many Requests" status code being returned, and subsequent requests will be blocked until the minute resets.
