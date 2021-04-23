---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

The Recursion.Space API is built on [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) principles. Our API has predictable resource-oriented URLs, accepts [form-encoded](<https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms>) request bodies, returns [JSON-encoded](https://www.json.org/json-en.html) responses, and uses standard HTTP response codes, authentication, and verbs.

API authentication is handled by a unique key generated for your account.

If you need API support or would like to see how others are implementing the platform you will find our staff and community through our Discord server.

<a target="_blank" rel="noopener noreferrer" href="https://discord.com/invite/KnFp4jd9AV" style="width: 100%">
<img src="https://discordapp.com/api/guilds/790311269420630079/widget.png?style=banner2" alt="Discord Banner 2" style="max-width: 100%; margin: auto; display: block;"/>
</a>

<aside class="notice">
BASE URL <code>https://api.recursion.space/v1/</code>
</aside>

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.recursion.space/v1/" \
  -H "Authorization: Token YOUR_API_KEY_HERE"
```

> Make sure to replace `meowmeowmeow` with your API key.

Recursion.Space uses API keys to allow access to the API. You can obtain an API key under the developer tab on your dashboard.

Your API key grants privlaged access to your account and by extention spaces, so be sure to keep it secure! Do not share your API keys in publicly accessible areas such as GitHUB, client-side code, and so forth.

`Token: YOUR API KEY HERE`

<aside class="warning">
All API requests must include the API key and be made over HTTPS, requests that do not meet these requirements will fail.
</aside>

# Language Libraries

Language libraries will be added as they become available, to find community libraries vist Discord.

# SPACE

## Operators Details

```shell
curl "https://api.recursion.space/v1/operators" \
  -H "Authorization: Token "
```

> The above command returns JSON for all operators, structured like this:

```json
[
  {
    "facility": ,
    "cardNumber": ,
    "phone_number": ,
    "address": ,
    "city": ,
    "state": ,
    "zip_code": ,
    "username": ,
    "first_name": ,
    "last_name": ,
    "email": ,
  }
]
```

Retrive information for all operators ("admins") of your space.

## Member Details

```shell
curl "https://api.recursion.space/v1/members/" \
  -H "Token: meowmeowmeow"
```

> The above command returns JSON for all members, structured like this:

```json
[
  {
    "cardNumber": "0123456789",
    "access_group": 123,
    "phone_number": "calico",
    "address": 6,
    "city": 7,
    "state": ,
    "zip_code": ,
    "username": ,
    "first_name": ,
    "last_name": ,
    "email": ,
    "restricted_nodes": []
  },
]
```

Retrive information for all members associated with your space.

### HTTP Request

`GET http://api.recursion.space/v1/members`

### Query Parameters

| Parameter        | Default | Description                                                               |
| ---------------- | ------- | ------------------------------------------------------------------------- |
| cardNumber       | null    | The RFID number assigned to your member.                                  |
| access_group     | null    | The ID for the access group that the member belongs to.                   |
| phone_number     | null    | Member provided phone number.                                             |
| address          | null    | Member provided address.                                                  |
| city             | null    | City component of address provided by member.                             |
| state            | null    | State component of address provided by member.                            |
| zip_code         | null    | Zip Code component of address provided by member.                         |
| username         | null    | Username assosiated with the members account.                             |
| first_name       | null    | Members first name.                                                       |
| last_name        | null    | Members last name.                                                        |
| email            | null    | Member provided email.                                                    |
| restricted_nodes | null    | List of ids the member does not have access to within their access group. |

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
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn')

let api = kittn.authorize('meowmeowmeow')
let max = api.kittens.get(2)
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

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the kitten to retrieve |

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
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn')

let api = kittn.authorize('meowmeowmeow')
let max = api.kittens.delete(2)
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the kitten to delete |

# HUB

# NODE
