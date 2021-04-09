---
parent: References
title: Terms and Concepts
---

# Terms and Concepts
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>


## Fleet
A fleet is the top level container for insurable objects and coverages and is added by Focus people. As our customer, you should receive a unique token for it before you start the API integration project. We call that uniq token ***fleet token***.

There are three types of fleets depending on the types of insurable objects underneath. We distinguish those three types of fleets as they are modeled differently in our system.
- Driver Only Fleet. This type of fleet would have drivers only. 
- Vehicle Only Fleet. This type of fleet would just contain vehiles but no drivers.
- Normal Fleet. This type of fleets would have contractors, vehicles and drivers.

Each type of fleet has its own API domain. You should not mess it up. However, there are validations in our end so you don't have to worry about using the wrong API domain.

## Product
A product identified by a ***product token*** wraps all the details of policies, as well as fees if there are any. It would be very convenient for you to add coverage with a product is set up.

## Insured
There are three categories for insurable objects.

| Category | Description|
|:---  |:--- |
| Contractor | Represents a business. | 
| Unit | Represents a vehicle. |
| Driver | Represents a person. |