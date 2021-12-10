---
description: A comprehensive list of the customer payment source resource's attributes and relationships.
---

# The customer payment source object

A customer payment source object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/customer_payment_sources` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `customer_payment_sources`                        |
| **id**         | `string` | The customer payment source unique identifier  |
| links.**self** | `string` | The customer payment source endpoint URL       |
| attributes.**name** | `string` | Returns the associated payment source's name |
| attributes.**customer_token** | `string` | Returns the customer gateway token stored in the gateway |
| attributes.**payment_source_token** | `string` | Returns the payment source token stored in the gateway |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**customer** | `object` | The associated customer. |
| relationships.**payment_source** | `object` | The associated payment source (i.e. credit card). |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

