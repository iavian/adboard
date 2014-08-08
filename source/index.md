---
title: API Reference for AdBoard

toc_footers:
  - © AdBoard</a>

includes:
  - errors

search: true
---

# Introduction

API endpoints for adboard
# Base URL
## Development
`http://adboard.iavian.net:8080/adboard`
## Production
TODO
# Authentication

> TODO, needs discussion

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

# User

## Create New User 

```shell
curl "/user"
```
> The above command returns JSON structured like this:

```json
  {
    "user": "uuid"
  }
```

This endpoint creates new user.

### HTTP Request

`POST /user`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | true |  email
accessToken | true | accessToken from gmail
refreshToken | true | from gmail 

<aside class="success">
Remember —  POST as JSON with application/json Content-Type
</aside>

# Scoop
## List Scoops

