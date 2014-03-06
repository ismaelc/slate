---
title: Concur API Reference

language_tabs:
  - shell
  - ruby
  - python

toc_footers:
 - <a href='https://developer.concur.com/register'>Sign Up for a Developer Key</a>
 - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
---

# Introduction

Explore the Concur Platform
Business travel is a $1 trillion industry, with U.S. business travelers logging 460M trips a year.* Concur enables businesses to manage everything from travel bookings to expenses and compliance requirements. And apps that integrate are in demand.

The in-product Concur App Center is designed for 20M travelers.  Find API Documentation, Forums, Sample Code, a sandbox tutorial and Get Started resources to put your app inside.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Concur's implementation of OAuth 2.0 requires a Concur user’s login ID or email address, and password or PIN (i.e., their “Concur credentials”). The partner application can either collect the credentials and send them to Concur (the Native flow) or send the user to a login page owned by Concur (the Web flow). The partner application requests an OAuth token from Concur, with either the login credentials or a code supplied to the application from the Concur OAuth web page. The partner application can then use the OAuth token in web service requests.

Concur expects for the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: OAuth <access token>`

<aside class="notice">
You must replace `<access token` with your access token.
</aside>

# AttendeeTypes

## Gets all attendee types

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
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
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Returns all active AttendeeTypes for the company.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/attendeetypes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset |  | Starting page offset.
limit | 25 | Number of records to return (default 25).

<aside class="success">
Remember — <insert note here>
</aside>

## Get a single AttendeeType by ID

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Returns an AttendeeType by ID.

<aside class="warning">Warning message here</aside>

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/attendeetypes/{id}`

### URL Parameters

Parameter | Description
--------- | -----------
id | AttendeeType ID.

# Errors

The Kittn API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The kitten requested is hidden for administrators only
404 | Not Found -- The specified kitten could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The kitten requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many kittens! Slown down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
