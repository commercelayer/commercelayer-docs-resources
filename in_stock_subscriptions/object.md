---
description: A comprehensive list of the in stock subscription resource's attributes and relationships.
---

# The in stock subscription object

An in stock subscription object is returned as part of the response body of each successful list, retrieve, create or update API call.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `in_stock_subscriptions`                        |
| **id**         | `string` | The in stock subscription unique identifier  |
| links.**self** | `string` | The in stock subscription endpoint URL       |
| attributes.**status** | `string` | The subscription status. One of 'active' (default), 'inactive', or 'notified' |
| attributes.**customer_email** | `string` | The email of the associated customer, replace the relationship |
| attributes.**sku_code** | `string` | The code of the associated sku, replace the relationship |
| attributes.**stock_threshold** | `integer` | The threshold at which to trigger the back in stock notification, default to 1. |
| attributes.**_activate** | `boolean, value is 'true'` | Send this attribute if you want to activate an inactive subscription. |
| attributes.**_deactivate** | `boolean, value is 'true'` | Send this attribute if you want to dactivate an active subscription. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**market** | `object` | The associated market. |
| relationships.**customer** | `object` | The associated customer. |
| relationships.**sku** | `object` | The associated sku. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

