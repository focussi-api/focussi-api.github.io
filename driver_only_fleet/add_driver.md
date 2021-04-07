---
parent: Driver Only Fleet
title: Add Driver
has_children: false
nav_order: 1
---

# Add Driver

## Information
Description
: This API allows you to add a driver to CBA. You can optionally add coverage for the driver in the same request.

Url
:  `/api/v2/dof/{fleet_token}/add_driver`

Method
: POST


## Body
```json
{
    "identifiers": 
    {
       "driver_number": "XXX1",
       "custom_idenfier_1": "XXX2",
       "custom_identifier_2": "XXX3"
    },
    "driver":
    {
        "first_name": "",
        "middle_name": "",
        "last_name": "",
        "dob": "0001-01-01",
        "email": "",
        "phone_number" :"",
        "cell_number": "",
        "address": "",
        "address2":"",
        "city":"",
        "state":"",
        "zip":"",
        "license": "",
        "license_state": "",
        "custom_fields": 
        {
            "custom_field_1": "",
            "custom_field_2": ""
        }
    },
    "coverages":
    [
        {
            "inception_date": "2021-01-01",
            "termination_date": "0001-01-01",
            "product_token": "",
            "options": 
            {
                "option_1": "",
                "option_2": ""
            } 
        }
    ]
}
```
## Parameters
1. `identifiers` is a required element. At least one key should be supplied. Any key with blank value will be ignored. The request would be rejected if `identifiers` is not valid. `driver_name` is a preserved built-in key. You could define any custom key and not use the preserved one. 

2. `driver` is a required element. You can have custom fields passed as well using the optional nested element `custom_fields`.

3. `coverages` is an optional element and is type of `Array`, but remember product_token should be unique for each item in the coverage list.

## Response
```json
{
    "success": "false",
    "error_code": "",
    "error_message": ""
}
```
1. The request would either succeed or fail as a whole. it will not be partially proccessed. 
2. Below is the list of possible error codes. Error message would be shown in the response as well.

    | Code | Description|
    |:---  |:--- |
    | InvalidInput | There could be several causes for this kind of failure. Eg: the json input cannot be parsed; identifiers not supplied; etc. | 
    | DriverExists | The request driver already exists in CBA. |
    

