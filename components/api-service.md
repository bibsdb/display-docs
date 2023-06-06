---
layout: default
title: API
parent: Components
nav_order: 1
---

# API service

We use a general API-first approach.
Therefore, all data is created and retrieved through API calls to the API service. 

## Tenants

Content in the API is connected to a Tenant. Each user is in x tenants.
This allows for multiple content silos in the same installation.

## Authentication

The API is stateless. Authentication is achieved through the `/authentication/token`
endpoint for admin and through the `/authentication/screen` endpoint.
