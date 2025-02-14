---
parent: Driver Only Fleet
title: Add Driver
nav_order: 1
---

# Add Driver
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

## Description 
This API allows you to add a driver to CBA. Optionally you can add coverage for the driver in the same request.


## Url 

```
https://{site}.focussi.com/api/v2/dof/add_driver
```
 

## Method 
```
POST
```


## Body 
 
```json
{
    "fleet_token": "<fleet_token>",
    "identifiers": 
    {
       "driver_number": "<driver_number>",
       "custom_idenfier_1": "<custom_idenfier_1>",
       "custom_identifier_2": "<custom_idenfier_2>"
    },
    "driver":
    {
        "first_name": "<first_name>",
        "middle_name": "<middle_name>",
        "last_name": "<last_name>",
        "dob": "<dob:Date>",
        "email": "<email>",
        "phone_number" :"<phone_number>",
        "cell_number": "<cell_number>",
        "address": "<address>",
        "address2":"<address2>",
        "city":"<city>",
        "state":"<state>",
        "zip":"<zip>",
        "license": "<license>",
        "license_state": "<license_state>",
        "custom_fields": 
        {
            "custom_field_1": "<custom_field_1>",
            "custom_field_2": "<custom_field_2>"
        }
    },
    "coverages":
    [
        {
            "inception_date": "<inception_date:Date>",
            "termination_date": "<termination_date:Date>",
            "product_token": "<product_token>",
            "options": 
            {
                "option_1": "<option_1>",
                "option_2": "<option_2>"
            } 
        }
    ]
}
```

## Parameters
- `fleet_token` Required. This if offered by IT department of Focus Solutions.
- `identifiers` Required. At least one key should be supplied. Any key with blank value will be ignored. The request would be rejected if `identifiers` is not valid. `driver_number` is a preserved built-in key. You could define any custom key and not use the preserved one. 

- `driver` Required. You can have custom fields passed as well using the optional nested element `custom_fields`.

- `coverages` Required. `Array` type. Remember product_token should be unique for each coverage item in the list.

## Response
```json
{
    "success": true|false,
    "error_code": "<error_code>",
    "error_message": "<error_message>"
}
```

- The request would either succeed or fail as a whole. it will not be partially proccessed. 
- Below is the list of possible error codes. Error message would be shown in the response as well.

    | Code | Description|
    |:---  |:--- |
    | InvalidInput | There could be several causes for this kind of failure. Eg: the json input cannot be parsed; identifiers not supplied; etc. | 
    | DriverExists | The request driver already exists in CBA. |
    
## Q&A
