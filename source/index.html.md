---
title: Blowout&Go API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: CURL
  - javascript: JavaScript
  - java: Java
  - swift: Swift

toc_footers:
  - <a href='https://bg-tech.github.io/slate/'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

#Upload

## Avatar

Endpoint dependencies includes (Sharp, Validator, Moment, File-Type, SHA1)

> Make sure to replace `xxxxxxxx` with your API key.

```shell
curl -0 -v -X POST "https://api.blowoutandgo.com/prod/upload/avatar" \
-H "x-api-key: xxxxxxxx" \
-H "Content-type: application/json" \
-d @- << EOF
{
    "user_id": 3239,
    "base64_image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfQAAAH0CA
    ..."
}
EOF
```

```javascript
// Check later
```

> The above command returns JSON structured like this on success:

```json
{
    "status": "ok",
    "original": "https://cdn.blowoutandgo.com/wp-content/uploads/sites/2/2017/08/1542_avatar.jpg",
    "thumbnail": "https://cdn.blowoutandgo.com/wp-content/uploads/sites/2/2017/08/1542_avatar-150x150.jpg",
    "small": "https://cdn.blowoutandgo.com/wp-content/uploads/sites/2/2017/08/1542_avatar-90x90.jpg"
}
```

> The above command returns JSON structured like this on failure:

```json
{
    "status": "error",
    "message": "File format not supported, use JPEG, PNG, TIFF, GIF and SVG"
}
```

### HTTP Request

`POST https://api.blowoutandgo.com/prod/upload/avatar`

### Request Body

Parameter | Default | Description
--------- | ------- | -----------
user_id | integer | Accepts user id for which image to be uploaded or updated.
base64_image | base64string | Accepts base 64 string. And only supports formats (JPEG, PNG, TIFF, GIF and SVG)

<aside class="warning">Error Messages</aside>

Code | Meaning | Message
---------- | ------- | -----------
400 | Bad Request | Missing input param user_id.
400 | Bad Request | Missing base64 header "data:[MIME];[ENCODING],[YOUR BASE64 STRING]".
400 | Bad Request | Not a valid base64 string.
422 | Unprocessable Entity| The string supplied is not a file type.
415 | Unsupported Media Type | File format not supported, use JPEG, PNG, TIFF, GIF and SVG.


## File

To be implemented

### HTTP Request

`POST https://api.blowoutandgo.com/prod/upload/file`

<aside class="notice">
API ENDPOINT NOT YET IMPLEMENTED. PLEASE CHECK LATER
</aside>

# Credits

Welcome to the BGTECH API! You can use our API to access BGX API endpoints, which can get information on various BGX Bookings, Stylists, Salons, BG Shop, and Orders in our database.