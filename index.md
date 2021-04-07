---
title: Home
nav_order: 1
---
# CBA Customer API
v2.0
{: .label .label-green }

## Introduction
This is the API documentation for customers to integrate with CBA. If you want to get the work automated for your company, this would be what you are looking for. It's better for you to understand following terms before you start.

### Fleet
A fleet is the top level container for insurable objects and coverages and is added by Focus people. As our customer, you should receive a unique token for it before you start the API integration project. We call that uniq token *fleet token*.

There are three types of fleets depending on the types of insurable objects underneath. We distinguish those three types of fleets as they are modeled differently in our system.
- Driver Only Fleet. This type of fleet would have drivers only. 
- Vehicle Only Fleet. This type of fleet would just contain vehiles but no drivers.
- Normal Fleet. This type of fleets would have contractors, vehicles and drivers.

Each type of fleet has its own API domain. You should not mess it up. However, there are validations in our end so you don't have to worry about using the wrong API domain.

### Product
A product, which is identified by a *product token*, wraps all the policy details inside, as well as fee options if there are any. This is very convenient for you to add coverage.

### Insured
There are three categories for insurable objects.

| Category | Description|
|:---  |:--- |
| Contractor | representing a business. | 
| Unit | representing a vehicle. |
| Driver | representing a person. |

### Coverage
A coverage could be added for any of the three different types of insured. 

## Conclusion
We use `BASIC AUTHENTICATION` to authenticate the API requests and process data in `JSON` format. You will receive an additional document with the authentication tokens from our technology department. Testing environment will also be offered to you before you move to production. Now let's find the right section of API from the navigation menu and give it a try. Good luck!

