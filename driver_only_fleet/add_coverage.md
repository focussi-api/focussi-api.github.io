---
parent: Driver Only Fleet
title: Add Coverage
has_children: false
nav_order: 4
---

# {{ page.title }
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
This API allows you to add coverage to an existing driver. Only one active coverage is allowed to be exist for the same product for given driver.

## Url 

```
https://{site}.focussi.com/api/v2/dof/add_coverage
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
- `fleet_token` Required. 
- `identifiers` Required.
- `coverages` Required. 

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
    | CoverageOverlapping | two coverages of the same type exist and are active on same day |
    
    
## Q&A
- **Q**: TO DO.

    **A**: TO DO.

