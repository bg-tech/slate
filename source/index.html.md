---
title: Blowout&Go API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='https://bg-tech.github.io/slate/'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the BGTECH BGX API! You can use our API to access BGX API endpoints, which can get information on various BGX Bookings, Stylists, Salons, BG Shop, and Orders in our database.

We have language bindings in NodeJS, PHP, Swift, and Java! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

#Coupons

## Assign

```json
{
    "status": "ok",
    "data": [
        {
            "id": 4142,
            "code": "abcd4321",
            "discount_type": "amount",
            "value": 150,
            "terms": "Coupon is valid for fab 5",
            "start_date": "2017-10-12T20:00:00.000Z",
            "expiry_date": "2018-04-12T20:00:00.000Z",
            "restricted_days": "a:0:{}",
            "client_id": null,
            "usage_limit": 5,
            "usage_count": 0,
            "is_bgx": "0"
        },
        {
            "id": 4141,
            "code": "abcd1234",
            "discount_type": "amount",
            "value": 150,
            "terms": "Coupon is valid for fab 5",
            "start_date": "2017-10-10T20:00:00.000Z",
            "expiry_date": "2018-04-10T20:00:00.000Z",
            "restricted_days": "a:0:{}",
            "client_id": null,
            "usage_limit": 5,
            "usage_count": 0,
            "is_bgx": "0"
        }
    ]
}
```

### HTTP Request

`GET https://api.blowoutandgo.com/prod/bgx-coupons`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the coupon to retrieve

> To authorize, use this code:

```json
{
    "status": "ok",
    "data": []
}
```

> Response JSON structured like this:

```json
{
    "status": "ok",
    "data": []
}
```

<aside class="success">
You must replace <code>xxxxxxxx</code> with your personal API key.
</aside>

## Validate

#Upload

## avatar

### HTTP Request

`POST https://api.blowoutandgo.com/prod/upload/avatar`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user_id | integer | Accepts user id for which image to be uploaded or updated.
base64_image | base64string | Accepts base 64 string. And only supports formats (JPEG, PNG, TIFF, GIF and SVG)

## Finish

# Bookings

## Cancel

### HTTP Request

`GET https://api.blowoutandgo.com/prod/bookings`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="notice">
You must replace <code>xxxxxxxx</code> with your personal API key.
</aside>



## Finish

### HTTP Request

`GET https://api.blowoutandgo.com/prod/bookings`
## Start

### HTTP Request

`GET https://api.blowoutandgo.com/prod/bookings`

# Authentication

> To authorize, use this code:

```php
import kittn

api = kittn.authorize('xxxxxxxx')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "x-api-key: xxxxxxxx"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('xxxxxxxx');
```

> Make sure to replace `xxxxxxxx` with your API key.

BGX uses API keys to allow access to the API. You can register a new BGX API key at our [developer portal](https://blowoutandgo.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: xxxxxxxx`

<aside class="notice">
You must replace <code>xxxxxxxx</code> with your personal API key.
</aside>

# BGX Bookings

## Get All BGX-Bookings

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all bookings.

### HTTP Request

`GET https://api.blowoutandgo.com/prod/bookings`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint retrieves a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

