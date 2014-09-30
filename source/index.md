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
  -H "Authorization: user-uuid"
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

```shell
curl "/scoop"
```
> The above command returns JSON structured like this:

```json

[
   {
      "id":"d72cf5f7-cad7-42fe-a709-3b4361387300",
      "imgobjs":{
         "img":[
            {
               "area":234360,
               "height":310,
               "width":756,
               "squareRatio":41.00529098510742,
               "src":"http://rm.recs.richrelevance.com/rrmail/imgreq?a=88ac00e4f3e16e44&version=2&zoneName=richmail&campaignId=77371&userId=483cdb9a2cb6c27af1fa83d499526643&date=07-18-2014&o=123&EMID=B2C_2016_0718_965_Cabinetry"
            }
         ]
      },
      "subject":"Additional Savings on Kitchen and Bath Cabinets, Travel, School Essentials and More!",
      "company":"Target"
   }
]

```

This endpoint gets all scoop for a user. the user has to be authorized

### HTTP Request

`GET /scoop/{page}/{limit}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
page | true  |  for pagination
limit | true | limits # of records


## Get a Scoop

```shell
curl "/scoop/{scoopid}"
```
> The above command returns JSON structured like this:

```json
   {
      "id":"d72cf5f7-cad7-42fe-a709-3b4361387300",
      "imgobjs":{
         "img":[
            {
               "area":234360,
               "height":310,
               "width":756,
               "squareRatio":41.00529098510742,
               "src":"http://rm.recs.richrelevance.com/rrmail/imgreq?a=88ac00e4f3e16e44&version=2&zoneName=richmail&campaignId=77371&userId=483cdb9a2cb6c27af1fa83d499526643&date=07-18-2014&o=123&EMID=B2C_2016_0718_965_Cabinetry"
            }
         ]
      },
      "subject":"Additional Savings on Kitchen and Bath Cabinets, Travel, School Essentials and More!",
      "company":"Target"
   }
```

This endpoint gets a scoop for the authorized user

### HTTP Request

`GET /scoop/{scoopid}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
scoopid | true |  id of the scoop as returned by /scoop list


## Delete a Scoop

```shell
curl "/scoop/{scoopid}"
```
> The above command returns JSON structured like this:

```json
   {
      "status":true
   }
```

This endpoint gets a scoop for the authorized user

### HTTP Request

`DELETE /scoop/{scoopid}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
scoopid | true |  id of the scoop as returned by /scoop list


# Mail
## Get a Mail

```shell
curl "/mail"
```
> The above command returns HTML:

```html

<html>...</html>

```

This endpoint gets all scoop for a user. the user has to be authorized

### HTTP Request

`GET /mail/{scoopid}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
scoopid | true  |  ScoopId
