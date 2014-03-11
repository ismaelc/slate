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

Explore the Concur Platform. 
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
  -H "Authorization: OAuth <access token>"
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
curl "https://www.concursolutions.com/api/v3.0/expense/attendeetypes?limit=25"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "AllowAttendeeCountEditing": "bool",
      "AllowManuallyEnteredAttendees": "bool",
      "AttendeeFormID": "string",
      "Code": "string",
      "ConnectorID": "string",
      "DuplicateSearchFields": [
        "string"
      ],
      "ID": "string",
      "Name": "string",
      "URI": "string"
    }
  ],
  "NextPage": "string"
}
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
curl "https://www.concursolutions.com/api/v3.0/expense/attendeetypes/123"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "AllowAttendeeCountEditing": "bool",
  "AllowManuallyEnteredAttendees": "bool",
  "AttendeeFormID": "string",
  "Code": "string",
  "ConnectorID": "string",
  "DuplicateSearchFields": [
    "string"
  ],
  "ID": "string",
  "Name": "string",
  "URI": "string"
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

## Delete an AttendeeType by ID

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
curl -X DELETE "https://www.concursolutions.com/api/v3.0/expense/attendeetypes/123"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json

```

Deletes the specified AttendeeType.

### HTTP Request

`DELETE https://www.concursolutions.com/api/v3.0/expense/attendeetypes/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id |  | ID of the AttendeeType to delete.

# DigitalTaxInvoices

## Gets all digital tax invoices

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
curl "https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices?limit=25"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "ID": "string",
      "URI": "string"
    }
  ],
  "NextPage": "string"
}
```

Returns all digital tax invoices that can be validated by the user based on the search criteria.


### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices?limit=25`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset |  | Starting page offset.
limit | 25 | Number of records to return (default 25).
modifiedafter | | Optional modified date of the queue record for the digital tax invoice. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    

## Gets a single Digital Tax Invoice by ID

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
curl "https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices/123"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "AccountID": "string",
  "ReceiptData": "string"
}
```

Returns a single Digital Tax Invoice by ID

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset |  | Starting page offset.
limit | 25 | Number of records to return (default 25).
modifiedafter | | Optional modified date of the queue record for the digital tax invoice. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.   

## Update a DigitalTaxInvoice by ID

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
curl -X PUT -H "Content-Type: application/json" -d '{"Comment":"string","Status":"string"}' https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices/123
-H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json

```

Updates the DigitalTaxInvoice specified in the URL.

### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/expense/digitaltaxinvoices/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
content |  | Status update to the Digital Tax Invoice
id | | ID of the Digital Tax Invoice to update 

# Entries

## Create a new expense entry

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
curl -X POST -H "Content-Type: application/json" -d '{TODO}' https://www.concursolutions.com/api/v3.0/expense/entries -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ID": "string",
  "URI": "string"
}
```

Creates a new expense entry

### HTTP Request

`POST https://www.concursolutions.com/api/v3.0/expense/entries`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
content | | Expense entry object to create
user | | Optional. The login ID of the user. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

# ExhangeRates

## Retrieve exchange rate

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
curl "https://www.concursolutions.com/api/v3.0/expense/exchangerates/?fromCurrency=USD&toCurrency=CAD&forDate=2012-12-20" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
    TODO
}
```

Retrieve exchange rate between two currencies on a given date.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/exchangerates/?fromCurrency={fromCurrency}&toCurrency={toCurrency}&forDate={forDate}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
fromCurrency | | The 3-letter ISO 4217 currency code for exchange from currency. Example: USD
toCurrency | | The 3-letter ISO 4217 currency code for exchange to currency. Example: CAD
forDate | | For date in YYYY-MM-DD format. Example: 2012-12-20. Dates older than 2000-01-01 will result in exchange rate of 1 and dates in the future will result in today's exchange rate.

# ExpenseGroupConfigurations

## Get an expense group configuration

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
curl "https://www.concursolutions.com/api/v3.0/expense/expensegroupconfigurations?limit=10" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "AllowUserDigitalTaxInvoice": "Boolean?",
      "AllowUserRegisterYodlee": "Boolean?",
      "AttendeeListFormID": "string",
      "AttendeeListFormName": "string",
      "AttendeeTypes": [
        {
          "Code": "string",
          "Name": "string"
        }
      ],
      "CashAdvance": {
        "AllowUserCarryBalance": "Boolean?",
        "AllowUserLinkMultiple": "Boolean?",
        "AllowUserUpdateExchangeRate": "Boolean?",
        "Name": "string",
        "WorkflowID": "string"
      },
      "ID": "string",
      "Name": "string",
      "PaymentTypes": [
        {
          "ID": "string",
          "IsDefault": "Boolean?",
          "Name": "string"
        }
      ],
      "Policies": [
        {
          "ExpenseTypes": [
            {
              "Code": "string",
              "ExpenseCode": "string",
              "Name": "string"
            }
          ],
          "ID": "string",
          "IsDefault": "Boolean?",
          "IsInheritable": "Boolean?",
          "Name": "string"
        }
      ],
      "URI": "string"
    }
  ],
  "NextPage": "string"
}
```

Get an expense group configuration owned by the user based on the search criteria.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/expensegroupconfigurations`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user | | Optional. The login ID of the user. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.
offset | | Starting page offset
limit | 10 | Determines the number of records to return (default 10)

## Gets an expense group configuration by ID

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
curl "https://www.concursolutions.com/api/v3.0/expense/expensegroupconfigurations/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "AllowUserDigitalTaxInvoice": "Boolean?",
  "AllowUserRegisterYodlee": "Boolean?",
  "AttendeeListFormID": "string",
  "AttendeeListFormName": "string",
  "AttendeeTypes": [
    {
      "Code": "string",
      "Name": "string"
    }
  ],
  "CashAdvance": {
    "AllowUserCarryBalance": "Boolean?",
    "AllowUserLinkMultiple": "Boolean?",
    "AllowUserUpdateExchangeRate": "Boolean?",
    "Name": "string",
    "WorkflowID": "string"
  },
  "ID": "string",
  "Name": "string",
  "PaymentTypes": [
    {
      "ID": "string",
      "IsDefault": "Boolean?",
      "Name": "string"
    }
  ],
  "Policies": [
    {
      "ExpenseTypes": [
        {
          "Code": "string",
          "ExpenseCode": "string",
          "Name": "string"
        }
      ],
      "ID": "string",
      "IsDefault": "Boolean?",
      "IsInheritable": "Boolean?",
      "Name": "string"
    }
  ],
  "URI": "string"
}
```

Gets an expense group configuration by ID.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/expensegroupconfigurations/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | Specifies the Expense Group Configuration ID
user | | Optional. The login ID of the user. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

# LatestBookings

## Get the latest hotel and air booking for a particular user

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
curl "https://www.concursolutions.com/api/v3.0/insights/latestbookings/" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Airlines": [
    {
      "BookingClass": "string",
      "Code": "string"
    }
  ],
  "Hotel": {
    "Location": "string",
    "StarRating": "Int32?"
  }
}
```

Get the latest hotel and air booking for a particular user.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/insights/latestbookings/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user | | Optional. The login ID of the user. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

# Opportunities

## Gets a collection of opportunities for a specified trip or for all trips that fall within a date range

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
curl "https://www.concursolutions.com/api/v3.0/insights/opportunities"
  -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "EndCityCode": "string",
      "EndDateLocal": "datetime",
      "EndPostalCode": "string",
      "ID": "string",
      "IsActive": "bool",
      "StartCityCode": "string",
      "StartDateLocal": "datetime",
      "StartPostalCode": "string",
      "TripId": "string",
      "Type": "string",
      "URI": "string"
    }
  ],
  "NextPage": "string"
}
```

Gets a collection of opportunities for a specified trip or for all trips that fall within a date range. Specify values for fromUtc and toUtc to get opportunities for a range of trips. Specify only tripId to get opportunities for a single trip. Specify OpportunityType to filter results by the specified opportunity types.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/insights/opportunities`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
tripId |  | The trip id    
opportunityType | | IComma separated list of opportunities (Hotel, Car, Air, Rail, Taxi and Service) to get. Do not specify any values to get all opportunities     
fromUtc | | The From date in UTC for the date range    
toUtc | | The To date in UTC for the date range    

# PurchaseOrderReceipts

## Updates purchase order line item with receipt information.

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
curl -X PUT -H "Content-Type: application/json" -d '{"IsReceived":"string","LineItemExternalID":"string","PurchaseOrderNumber":"string","ReceivedDate":"string","ReceivedQuantity":"string"}' https://www.concursolutions.com/api/v3.0/invoice/purchaseorderreceipts
-H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ErrorCode": "string",
  "ErrorMessage": "string",
  "FieldCode": "string",
  "LineItemExternalID": "string",
  "Message": "string",
  "PurchaseOrderNumber": "string",
  "Status": "string"
}
```

Updates purchase order line item with receipt information and returns status of updation.

### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/invoice/purchaseorderreceipts`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
purchaseOrderReceipt |  | Purchase Order Receipt information.  

# PurchaseOrders

## Create a new purchase order

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
curl -X POST -H "Content-Type: application/json" -d '{TODO}' https://www.concursolutions.com/api/v3.0/invoice/purchaseorders -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ErrorCode": "string",
  "ErrorMessage": "string",
  "FieldCode": "string",
  "LineItemExternalID": "string",
  "Message": "string",
  "PurchaseOrderNumber": "string",
  "Status": "string"
}
```

Creates a purchase order and returns the status of creation.


### HTTP Request

`POST https://www.concursolutions.com/api/v3.0/invoice/purchaseorders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
purchaseOrder |  | The purchase order details. 

## Updates an existing purchase order

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
curl -X PUT -H "Content-Type: application/json" -d '{TODO}' https://www.concursolutions.com/api/v3.0/invoice/purchaseorders -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ErrorCode": "string",
  "ErrorMessage": "string",
  "FieldCode": "string",
  "LineItemExternalID": "string",
  "Message": "string",
  "PurchaseOrderNumber": "string",
  "Status": "string"
}
```

Updates an existing purchase order and returns the status of the request.


### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/invoice/purchaseorders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
purchaseOrder |  | The purchase order details. 

## Retrieves an existing purchase order

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
curl https://www.concursolutions.com/api/v3.0/invoice/purchaseorders/123 -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "BillToAddress": {
    "Address1": "string",
    "Address2": "string",
    "Address3": "string",
    "City": "string",
    "CountryCode": "string",
    "ExternalID": "string",
    "Name": "string",
    "PostalCode": "string",
    "StateProvince": "string"
  },
  "CurrencyCode": "string",
  "Custom1": "string",
  "Custom10": "string",
  "Custom11": "string",
  "Custom12": "string",
  "Custom13": "string",
  "Custom14": "string",
  "Custom15": "string",
  "Custom16": "string",
  "Custom17": "string",
  "Custom18": "string",
  "Custom19": "string",
  "Custom2": "string",
  "Custom20": "string",
  "Custom21": "string",
  "Custom22": "string",
  "Custom23": "string",
  "Custom24": "string",
  "Custom3": "string",
  "Custom4": "string",
  "Custom5": "string",
  "Custom6": "string",
  "Custom7": "string",
  "Custom8": "string",
  "Custom9": "string",
  "Description": "string",
  "DiscountPercentage": "string",
  "DiscountTerms": "string",
  "ID": "string",
  "LineItem": [
    {
      "AccountCode": "string",
      "Allocation": [
        {
          "Amount": "string",
          "Custom1": "string",
          "Custom10": "string",
          "Custom11": "string",
          "Custom12": "string",
          "Custom13": "string",
          "Custom14": "string",
          "Custom15": "string",
          "Custom16": "string",
          "Custom17": "string",
          "Custom18": "string",
          "Custom19": "string",
          "Custom2": "string",
          "Custom20": "string",
          "Custom3": "string",
          "Custom4": "string",
          "Custom5": "string",
          "Custom6": "string",
          "Custom7": "string",
          "Custom8": "string",
          "Custom9": "string"
        }
      ],
      "CreateDate": "string",
      "Custom1": "string",
      "Custom10": "string",
      "Custom11": "string",
      "Custom12": "string",
      "Custom13": "string",
      "Custom14": "string",
      "Custom15": "string",
      "Custom16": "string",
      "Custom17": "string",
      "Custom18": "string",
      "Custom19": "string",
      "Custom2": "string",
      "Custom20": "string",
      "Custom3": "string",
      "Custom4": "string",
      "Custom5": "string",
      "Custom6": "string",
      "Custom7": "string",
      "Custom8": "string",
      "Custom9": "string",
      "Description": "string",
      "ExpenseType": "string",
      "ExternalID": "string",
      "IsReceiptRequired": "string",
      "LineNumber": "string",
      "Quantity": "string",
      "RequestedBy": "string",
      "RequestedDeliveryDate": "string",
      "SupplierPartID": "string",
      "Tax": "string",
      "UnitPrice": "string"
    }
  ],
  "Name": "string",
  "NeededByDate": "string",
  "OrderDate": "string",
  "PaymentTerms": "string",
  "PolicyExternalID": "string",
  "PurchaseOrderNumber": "string",
  "RequestedBy": "string",
  "RequestedDeliveryDate": "string",
  "Shipping": "string",
  "ShippingDescription": "string",
  "ShippingMethodKey": "string",
  "ShippingTermsKey": "string",
  "ShipToAddress": {
    "Address1": "string",
    "Address2": "string",
    "Address3": "string",
    "City": "string",
    "CountryCode": "string",
    "ExternalID": "string",
    "Name": "string",
    "PostalCode": "string",
    "StateProvince": "string"
  },
  "Tax": "string",
  "URI": "string",
  "VendorAccountNumber": "string",
  "VendorAddressCode": "string",
  "VendorCode": "string"
}
```

Gets an existing purchase order.

### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/invoice/purchaseorders/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id |  | The identifier for the purchase order. 

# QuickExpenses

## Gets all quick expenses

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
curl "https://www.concursolutions.com/api/v3.0/expense/quickexpenses?limit=25" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "Comment": "string",
      "CurrencyCode": "string",
      "ExpenseTypeCode": "string",
      "ExpenseTypeName": "string",
      "ID": "string",
      "LocationName": "string",
      "OwnerLoginID": "string",
      "OwnerName": "string",
      "PaymentTypeCode": "string",
      "ReceiptImageID": "string",
      "TransactionAmount": "Decimal?",
      "TransactionDate": "DateTime?",
      "URI": "string",
      "VendorDescription": "string"
    }
  ],
  "NextPage": "string"
}
```

Returns all QuickExpenses owned by the user.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/quickexpenses`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset |  | Starting page offset
limit | 25 | Number of records to return (default 25)
user |  | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Get a single QuickExpense by ID

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
curl "https://www.concursolutions.com/api/v3.0/expense/quickexpenses/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Comment": "string",
  "CurrencyCode": "string",
  "ExpenseTypeCode": "string",
  "ExpenseTypeName": "string",
  "ID": "string",
  "LocationName": "string",
  "OwnerLoginID": "string",
  "OwnerName": "string",
  "PaymentTypeCode": "string",
  "ReceiptImageID": "string",
  "TransactionAmount": "Decimal?",
  "TransactionDate": "DateTime?",
  "URI": "string",
  "VendorDescription": "string"
}
```

Returns a QuickExpense by ID.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/quickexpenses/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | QuickExpense ID
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Create a new QuickExpense

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
curl -X -POST -H "Content-Type: application/json" -d {TODO} "https://www.concursolutions.com/api/v3.0/expense/quickexpenses" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ID": "string",
  "URI": "string"
}
```

Creates a new QuickExpense

### HTTP Request

`POST https://www.concursolutions.com/api/v3.0/expense/quickexpenses`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
content | | QuickExpense object to create
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Update a QuickExpense by ID

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
curl -X PUT -H "Content-Type: application/json" -d {TODO} "https://www.concursolutions.com/api/v3.0/expense/quickexpenses/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  TODO
}
```

Updates the QuickExpense specified in the URL. Only the fields provided in the supplied object will be updated, missing fields will not be altered.

### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/expense/quickexpenses`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | QuickExpense ID
content | | Partial or complete QuickExpense object to update
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Delete a QuickExpense by ID

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
curl -X DELETE "https://www.concursolutions.com/api/v3.0/expense/quickexpenses/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  TODO
}
```

Deletes the specified QuickExpense

### HTTP Request

`DELETE https://www.concursolutions.com/api/v3.0/expense/quickexpenses/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | ID of the QuickExpense to delete
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

#ReceiptImages

![ReceiptImages](http://chrispogeek.files.wordpress.com/2014/01/expense-center-chris-ismael.png)

## Get all receipt IDs by user

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
curl "https://www.concursolutions.com/api/v3.0/expense/receiptimages?limit=25" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "ID": "string",
      "URI": "string"
    }
  ],
  "NextPage": "string"
}
```
Get a list of all receipt IDs owned by the user associated with the OAuth token

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/receiptimages?limit=25`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset | | Starting page offset    
limit | 25 | 
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Get a receipt image URL

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
curl "https://www.concursolutions.com/api/v3.0/expense/receiptimages/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ID": "string",
  "URI": "string"
}
```
Get a receipt image URL by image ID.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/receiptimages/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | ReceiptImage ID       
user |  | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.

## Create a new receipt image

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
curl -X POST "https://www.concursolutions.com/api/v3.0/expense/receiptimages" -H "Authorization: OAuth <access token>" TODO image body
```

> The above command returns JSON structured like this:

```json
{
  "ID": "string",
  "URI": "string"
}
```
Creates a new image in the receipt store.

### HTTP Request

`POST https://www.concursolutions.com/api/v3.0/expense/receiptimages`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.           
image |  | Image data file

## Appends a receipt image to an existing receipt image

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
curl -X PUT "https://www.concursolutions.com/api/v3.0/expense/receiptimages/123" -H "Authorization: OAuth <access token>" TODO image body
```

> The above command returns JSON structured like this:

```json
{
  TODO
}
```
Appends a receipt image to an existing image in the receipt store.

### HTTP Request

`PUT https://www.concursolutions.com/api/v3.0/expense/receiptimages/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | ID of the receipt image to update            
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    
image |  | Image data file

## Deletes a receipt image by ID

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
curl -X DELETE "https://www.concursolutions.com/api/v3.0/expense/receiptimages/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  TODO
}
```
Deletes the specified receipt image

### HTTP Request

`DELETE https://www.concursolutions.com/api/v3.0/expense/receiptimages/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | ID of the receipt image to delete              
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.   

# ReportDigests

## Get all ReportDigests

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
curl "https://www.concursolutions.com/api/v3.0/expense/reportdigests?limit=100" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "ApprovalStatusCode": "string",
      "ApprovalStatusName": "string",
      "ApproverLoginID": "string",
      "ApproverName": "string",
      "Country": "string",
      "CountrySubdivision": "string",
      "CreateDate": "DateTime?",
      "CurrencyCode": "string",
      "ID": "string",
      "LastComment": "string",
      "Name": "string",
      "OwnerLoginID": "string",
      "OwnerName": "string",
      "PaidDate": "DateTime?",
      "PaymentStatusCode": "string",
      "PaymentStatusName": "string",
      "ProcessingPaymentDate": "DateTime?",
      "ReportHeaderLastModifiedDate": "DateTime?",
      "SubmitDate": "DateTime?",
      "Total": "Decimal?",
      "URI": "string",
      "UserDefinedDate": "DateTime?"
    }
  ],
  "NextPage": "string"
}
```
Returns all ReportDigests owned by the user based on the search criteria.


### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/reportdigests`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
offset | | Starting page offset    
limit | | Number of records to return (default 100)    
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    
approvalStatusCode | | The status code for the Approval Status. FORMAT: list the status codes    
paymentStatusCode | | The status code for the Payment Status     FORMAT: list the status codes    
currencyCode | | The 3-letter ISO 4217 currency code for the report currency. Example: USD.    
paymentType | | The unique identifier for the payment type that is the payment type for at least one expense entry in the report. Use PaymentTypeID from Response of GET Expense Group Configurations V3.    
reimbursementMethod | | The method the report owner will be reimbursed. FORMAT: ADPPAYR - ADP Payroll; APCHECK - AP (Company Check); CNQRPAY - Expense Pay; PMTSERV - Other Payment Service. NOTE: PAY_PAL is NOT supported.    
approverLoginID | | the login ID for the report approver that is the current approver assigned to the report.    
expenseTypeCode | | the expense type code that is the expense type for at least one expense entry in the report. Use ExpenseTypeCode from Response of GET Expense Group Configurations V3.    
countryCode | | The report country. Maximum 2 characters. Format: The ISO 3166-1 alpha-2 country code. Example: United States is US.    
batchID | | The unique identifier for a payment batch where there is at least one report payee within the report. Use the BatchID from Response of GET Payment Batch List.    
vendorName | | The Vendor Description that is the vendor for at least one expense entry in the report.    
hasVAT | | The hasVAT flag for the report. FORMAT: true or false.    
hasImages | | The hasImages flag for the report. FORMAT: true or false.    
hasAttendees | | The hasAttendees flag for the report. FORMAT: true or false.    
hasBillableExpenses | | The IsBillable flag for at least one expense entry in the report. FORMAT: true or false.    
isTestUser | | The IsTestUser flag for the report owner. FORMAT: true or false.    
expenseGroupConfigID | | The unique identifier for the expense group configuration associated to the report's expense group. Use the ID from the Response of the Expense Group Configurations V3.    
costObject | | The list item code for an allocation field for at least allocation in the report.    
entryTransactionDateBefore | | The entry transaction date for at least one expense entry in the report is before this date.Format: YYYY-MM-DD    
entryTransactionDateAfter | | The entry transaction date for at least one expense entry in the report is after this date.Format: YYYY-MM-DD    
createDateBefore | | The report create date is before this date.Format: YYYY-MM-DD    
createDateAfter | | The report create date is after this date.Format: YYYY-MM-DD    
userDefinedDateBefore | | The report user defined date is before this date.Format: YYYY-MM-DD    
userDefinedDateAfter | | The report user defined date is after this date.Format: YYYY-MM-DD    
submitDateBefore | | The report submit date is before this date.Format: YYYY-MM-DD    
submitDateAfter | | the report submit date is after this date.Format: YYYY-MM-DD    
processingPaymentDateBefore | | The report processing payment date is before this date.Format: YYYY-MM-DD    
processingPaymentDateAfter | | The report processing payment date is after this date. Format: YYYY-MM-DD    
paidDateBefore | | The report paid date is before this date.Format: YYYY-MM-DD    
paidDateAfter | | The report paid date is after this date.Format: YYYY-MM-DD    
modifiedDateBefore | | The report modified date is before this date.Format: YYYY-MM-DD    
modifiedDateAfter | | The report modified date is after this date.Format: YYYY-MM-DD    

## Get a single ReportDigest by ID

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
curl "https://www.concursolutions.com/api/v3.0/expense/reportdigests/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "ApprovalStatusCode": "string",
  "ApprovalStatusName": "string",
  "ApproverLoginID": "string",
  "ApproverName": "string",
  "Country": "string",
  "CountrySubdivision": "string",
  "CreateDate": "DateTime?",
  "CurrencyCode": "string",
  "ID": "string",
  "LastComment": "string",
  "Name": "string",
  "OwnerLoginID": "string",
  "OwnerName": "string",
  "PaidDate": "DateTime?",
  "PaymentStatusCode": "string",
  "PaymentStatusName": "string",
  "ProcessingPaymentDate": "DateTime?",
  "ReportHeaderLastModifiedDate": "DateTime?",
  "SubmitDate": "DateTime?",
  "Total": "Decimal?",
  "URI": "string",
  "UserDefinedDate": "DateTime?"
}
```
Returns a ReportDigest by ID.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/expense/reportdigests/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | ReportDigest ID    
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    

# Requests

## Get a Travel Request by ID

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
curl "https://www.concursolutions.com/api/v3.0/travelrequest/requests/123" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "AgencyOfficeName": "string",
  "ApprovalLimitDate": "DateTime?",
  "ApprovalStatusName": "string",
  "AuthorizedDate": "DateTime?",
  "CashAdvanceCount": "int",
  "CashAdvancesList": [
    {
      "AmountRequested": "string",
      "ApprovalStatusName": "string",
      "CommentCount": "int",
      "CommentsList": [
        {
          "Comment": "string",
          "CommentDateTime": "DateTime?",
          "FirstName": "string",
          "LastName": "string"
        }
      ],
      "CurrencyCode": "string",
      "CurrencyName": "string",
      "EmployeeCurrencyCode": "string",
      "EmployeeCurrencyName": "string",
      "ExchangeRate": "string",
      "IssueDate": "DateTime?",
      "RequestDate": "DateTime?",
      "StartingBalance": "string"
    }
  ],
  "CommentCount": "int",
  "CommentsList": [
    "Comments"
  ],
  "CreationDate": "DateTime?",
  "CurrencyCode": "string",
  "Custom1": "string",
  "Custom10": "string",
  "Custom11": "string",
  "Custom12": "string",
  "Custom13": "string",
  "Custom14": "string",
  "Custom15": "string",
  "Custom16": "string",
  "Custom17": "string",
  "Custom18": "string",
  "Custom19": "string",
  "Custom2": "string",
  "Custom20": "string",
  "Custom3": "string",
  "Custom4": "string",
  "Custom5": "string",
  "Custom6": "string",
  "Custom7": "string",
  "Custom8": "string",
  "Custom9": "string",
  "EmployeeName": "string",
  "EndDate": "string",
  "EndTime": "string",
  "EntriesList": [
    {
      "AllocationCount": "int",
      "AllocationsList": [
        {
          "Custom1": "string",
          "Custom10": "string",
          "Custom11": "string",
          "Custom12": "string",
          "Custom13": "string",
          "Custom14": "string",
          "Custom15": "string",
          "Custom16": "string",
          "Custom17": "string",
          "Custom18": "string",
          "Custom19": "string",
          "Custom2": "string",
          "Custom20": "string",
          "Custom3": "string",
          "Custom4": "string",
          "Custom5": "string",
          "Custom6": "string",
          "Custom7": "string",
          "Custom8": "string",
          "Custom9": "string",
          "Percentage": "string"
        }
      ],
      "ApprovedAmount": "string",
      "CommentCount": "int",
      "CommentsList": [
        "Comments"
      ],
      "Custom1": "string",
      "Custom10": "string",
      "Custom11": "string",
      "Custom12": "string",
      "Custom13": "string",
      "Custom14": "string",
      "Custom15": "string",
      "Custom16": "string",
      "Custom17": "string",
      "Custom18": "string",
      "Custom19": "string",
      "Custom2": "string",
      "Custom20": "string",
      "Custom21": "string",
      "Custom22": "string",
      "Custom23": "string",
      "Custom24": "string",
      "Custom25": "string",
      "Custom26": "string",
      "Custom27": "string",
      "Custom28": "string",
      "Custom29": "string",
      "Custom3": "string",
      "Custom30": "string",
      "Custom31": "string",
      "Custom32": "string",
      "Custom33": "string",
      "Custom34": "string",
      "Custom35": "string",
      "Custom36": "string",
      "Custom37": "string",
      "Custom38": "string",
      "Custom39": "string",
      "Custom4": "string",
      "Custom40": "string",
      "Custom5": "string",
      "Custom6": "string",
      "Custom7": "string",
      "Custom8": "string",
      "Custom9": "string",
      "EntryDescription": "string",
      "ExceptionCount": "int",
      "ExceptionsList": [
        {
          "ExceptionCode": "string",
          "ExceptionLevel": "int",
          "ExceptionMessage": "string"
        }
      ],
      "ExchangeRate": "string",
      "ExpenseTypeName": "string",
      "ForeignAmount": "string",
      "ForeignCurrencyName": "string",
      "LastModifiedDate": "DateTime?",
      "OrgUnit1": "string",
      "OrgUnit2": "string",
      "OrgUnit3": "string",
      "OrgUnit4": "string",
      "OrgUnit5": "string",
      "OrgUnit6": "string",
      "PostedAmount": "string",
      "RemainingAmount": "string",
      "SegmentCount": "int",
      "SegmentsList": [
        {
          "ApprovedAmount": "string",
          "ArrivalDate": "string",
          "ArrivalTime": "string",
          "ClassOfServiceCode": "string",
          "CommentCount": "int",
          "CommentsList": [
            "Comments"
          ],
          "Custom1": "string",
          "Custom10": "string",
          "Custom11": "string",
          "Custom12": "string",
          "Custom13": "string",
          "Custom14": "string",
          "Custom15": "string",
          "Custom16": "string",
          "Custom17": "string",
          "Custom18": "string",
          "Custom19": "string",
          "Custom2": "string",
          "Custom20": "string",
          "Custom21": "string",
          "Custom22": "string",
          "Custom23": "string",
          "Custom24": "string",
          "Custom25": "string",
          "Custom26": "string",
          "Custom27": "string",
          "Custom28": "string",
          "Custom29": "string",
          "Custom3": "string",
          "Custom30": "string",
          "Custom31": "string",
          "Custom32": "string",
          "Custom33": "string",
          "Custom34": "string",
          "Custom35": "string",
          "Custom36": "string",
          "Custom37": "string",
          "Custom38": "string",
          "Custom39": "string",
          "Custom4": "string",
          "Custom40": "string",
          "Custom5": "string",
          "Custom6": "string",
          "Custom7": "string",
          "Custom8": "string",
          "Custom9": "string",
          "DepartureDate": "string",
          "DepartureTime": "string",
          "ExceptionCount": "int",
          "ExceptionsList": [
            "TRException"
          ],
          "ExchangeRate": "string",
          "FlightNumber": "string",
          "ForeignAmount": "string",
          "ForeignCurrencyName": "string",
          "FromLocationDetail": "string",
          "FromLocationName": "string",
          "IsAgencyBooked": "string",
          "IsSelfBooked": "string",
          "LastModifiedDate": "DateTime?",
          "PostedAmount": "string",
          "RecordLocator": "string",
          "RemainingAmount": "string",
          "SegmentLocator": "string",
          "SegmentType": "string",
          "ToLocationDetail": "string",
          "ToLocationName": "string",
          "TripLocator": "string"
        }
      ],
      "TransactionDate": "DateTime?"
    }
  ],
  "EntryCount": "int",
  "EverSentBack": "string",
  "ExceptionCount": "int",
  "ExceptionsList": [
    "TRException"
  ],
  "ExtensionOf": "string",
  "HasException": "string",
  "LastModifiedDate": "DateTime?",
  "LoginID": "string",
  "Purpose": "string",
  "RequestID": "string",
  "RequestName": "string",
  "RequestTotal": "string",
  "StartDate": "string",
  "StartTime": "string",
  "SubmitDate": "DateTime?",
  "TotalApprovedAmount": "string",
  "TotalRemainingAmount": "string",
  "WorkflowUrl": "string"
}
```
Returns a Travel Request by ID.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/travelrequest/requests/{id}`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | | Travel Request ID
user | | Optional login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    

## Get all Requests

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
curl "https://www.concursolutions.com/api/v3.0/travelrequest/requests?status=ACTIVE&offset=0&limit=25" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "RequestsList": [
    {
      "ApprovalStatus": "string",
      "ApproverLoginID": "string",
      "EmployeeName": "string",
      "EndDate": "DateTime?",
      "LastComment": "string",
      "Purpose": "string",
      "RequestCurrency": "string",
      "RequestDate": "DateTime?",
      "RequestDetailsUrl": "string",
      "RequestID": "string",
      "RequestName": "string",
      "RequestTotal": "string",
      "RequestUserLoginID": "string",
      "StartDate": "DateTime?"
    }
  ],
  "TotalCount": "int"
}
```
Returns all Requests owned by the user.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/travelrequest/requests`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user | | Login ID of the user to act on the behalf of. The access token owner must have the Web Services Admin (Professional) or Can Administer (Standard) user role to use this parameter.    
status | | The Status search term specifies which travel request or approval status to return. If no Status value is sent, the default Status of Active will be used.    
modifiedAfter | | This returns travel requests in which the associated dependents (header, entries, segments, allocations, attendees, comments ) were modified after the specified date and time. This search term can be used along with other search terms to narrow the results. The date and time (if desired) should be in UTC. The format is: YYYY-MM-DDThh:mm:ss.    
modifiedBefore | | This returns travel requests in which the associated dependents (header, entries, segments, allocations, attendees, comments ) were modified before the specified date and time.This search term can be used along with other search terms to narrow the results. The date and time (if desired) should be in UTC. The format is: YYYY-MM-DDThh:mm:ss.    
offset | 0 | Starting page offset (default 0)    
limit | 25 | Number of records to return (default 25)    

# Vendors

## Retrieves an existing vendor

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
curl "https://www.concursolutions.com/api/v3.0/invoice/vendors" -H "Authorization: OAuth <access token>"
```

> The above command returns JSON structured like this:

```json
{
  "Items": [
    {
      "Address1": "string",
      "Address2": "string",
      "Address3": "string",
      "AddressCode": "string",
      "Approved": "string",
      "BuyerAccountNumber": "string",
      "City": "string",
      "ContactEmail": "string",
      "ContactFirstName": "string",
      "ContactLastName": "string",
      "ContactPhoneNumber": "string",
      "Country": "string",
      "CountryCode": "string",
      "CurrencyCode": "string",
      "Custom1": "string",
      "Custom10": "string",
      "Custom11": "string",
      "Custom12": "string",
      "Custom13": "string",
      "Custom14": "string",
      "Custom15": "string",
      "Custom16": "string",
      "Custom17": "string",
      "Custom18": "string",
      "Custom19": "string",
      "Custom2": "string",
      "Custom20": "string",
      "Custom3": "string",
      "Custom4": "string",
      "Custom5": "string",
      "Custom6": "string",
      "Custom7": "string",
      "Custom8": "string",
      "Custom9": "string",
      "DefaultEmployeeID": "string",
      "DefaultExpenseTypeName": "string",
      "DiscountPercentage": "string",
      "DiscountTermsDays": "string",
      "PaymentMethodType": "string",
      "PaymentTerms": "string",
      "PostalCode": "string",
      "PurchaseOrderContactEmail": "string",
      "PurchaseOrderContactFirstName": "string",
      "PurchaseOrderContactLastName": "string",
      "PurchaseOrderContactPhoneNumber": "string",
      "ShippingMethod": "string",
      "ShippingTerms": "string",
      "State": "string",
      "TaxID": "string",
      "URI": "string",
      "VendorCode": "string",
      "VendorName": "string"
    }
  ],
  "NextPage": "string",
  "Vendor": [
    "Vendor"
  ]
}
```
Gets an existing vendor.

### HTTP Request

`GET https://www.concursolutions.com/api/v3.0/invoice/vendors`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
limit | | The maximum number of items to be returned in a response. The default is 25 and cannot exceed 1000.    
offset | | Specifies the starting point for the next query when iterating through the collection response. Use with paged collections of resources.    
sortDirection | | ascending or descending, The default value will be ascending.    
sortBy | | Field you need to the results to be sorted by. Vendor Name will be made default if no value is sent. Only fields that are added to the vendor form can be used here. Fields have to be specified by name as specified in Doc.    
searchType | | Valid Options - exact, begins, contains and ends - Applies for the entire given search parameters. The default value if not sent is exact.    
vendorCode | | Vendor Code to be searched    
vendorName | | Vendor Name to be searched    
taxID | | Tax ID to be searched    
buyerAccountNumber | | Buyer Account Number to be searched    
addressCode | | Address Code to be searched    
address1 | | Address 1 to be searched    
address2 | | Address 2 to be searched    
address3 | | Address 3 to be searched    
city | | City to be searched    
state | | State to be searched    
postalCode | | Postal Code to be searched    
approved | | Find Approved/Un Approved Vendors , True/False    
country | | Country to be searched    
custom1 | | Custom 1 to be searched
custom2 | | Custom 2 to be searched
custom3 | | Custom 3 to be searched
custom4 | | Custom 4 to be searched
custom5 | | Custom 5 to be searched
custom6 | | Custom 6 to be searched
custom7 | | Custom 7 to be searched
custom8 | | Custom 8 to be searched
custom9 | | Custom 9 to be searched
custom10 | | Custom 10 to be searched
custom11 | | Custom 11 to be searched
custom12 | | Custom 12 to be searched
custom13 | | Custom 13 to be searched
custom14 | | Custom 14 to be searched
custom15 | | Custom 15 to be searched



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
