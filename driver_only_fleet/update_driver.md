---
parent: Driver Only Fleet
title: Update Driver
has_children: false
nav_order: 2
---

# Update Driver
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
This API allows you to update an existing driver in CBA. Coverages will not be changed.


## Url 

```
https://{site}.focussi.com/api/v2/dof/update_driver
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
    }
}
```

## Parameters
- `fleet_token` Required. This if offered by IT department of Focus Solutions.
- `identifiers` Required. At least one key should be supplied. The identifiers will be used to match the drivers in CBA under the fleet. If no driver or more than one drivers get matched, the request would fail.
- `driver` Required. The driver will be updated with the provided information.

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
    | NoDriver | The request driver does not exist in CBA. |
    | MultipleDriversFound | More than one drivers are matched by given identifiers. |
    
## Q&A
- **Q**: If a driver field has a blank value, will it the field remain changed or be cleared in CBA?

    **A**: It will be cleared. Don't include the filed in the request if you would not like to change it.

