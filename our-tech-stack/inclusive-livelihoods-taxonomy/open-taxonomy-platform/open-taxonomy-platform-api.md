---
description: >-
  Labor markets are diverse and fast changing, so a useful taxonomy must be
  localizable and adaptable in a transparent way. Learn more about the API that
  powers our open taxonomy platform.
---

# Open Taxonomy Platform API

## Overview and Format

The [Open Taxonomy Platform](./) API provides secure access to taxonomy models, occupations, skills, and their respective groups, enabling seamless integration with your applications. The base URL for all API requests is [https://platform.tabiya.tech/taxonomy/api-doc/swagger/](https://platform.tabiya.tech/taxonomy/api-doc/swagger/). To ensure standardized communication, all requests and responses (except file uploads) utilize the JSON format, making it straightforward to integrate with any modern programming environment.

## Credentials and Authentication

Before integration, developers must obtain the necessary credentials. An API key can be requested by contacting the admins via email at the dedicated address. Once issued, the API key must be included in every request sent to the API.

## Direct Access to the OpenAPI Specification

Two access methods are available for the API specifications. The primary method is through the interactive Swagger UI documentation, which allows browsing and live testing of all endpoints. Crucially, for developers looking to quickly configure their clients, a direct, standalone link to the OpenAPI v3 JSON specification file is provided. This link is essential for developers who want to import the entire API definition into tools like Postman or Insomnia (using the _Import > Link option_), accelerating setup by automatically generating all endpoint, parameter, and schema definitions:

* OpenAPI Specification link: [https://platform.tabiya.tech/taxonomy/api-doc/swagger/tabiya-api.json](https://platform.tabiya.tech/taxonomy/api-doc/swagger/tabiya-api.json)
* Swagger UI link: [https://platform.tabiya.tech/taxonomy/api-doc/swagger/](https://platform.tabiya.tech/taxonomy/api-doc/swagger/)
* ReDoc UI link: [https://platform.tabiya.tech/taxonomy/api-doc/redoc/](https://platform.tabiya.tech/taxonomy/api-doc/redoc/)

