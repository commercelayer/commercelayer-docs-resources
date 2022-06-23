---
description: A comprehensive list of the price volume tier resource's attributes and relationships
---

# The price volume tier object

A price volume tier object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/price_volume_tiers` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `price_volume_tiers`                        |
| **id**         | `string` | The price volume tier unique identifier  |
| links.**self** | `string` | The price volume tier endpoint URL       |
| attributes.**name** | `string` | The price tier's name |
| attributes.**up_to** | `float` | The tier upper limit. When 'null' it means infinity (useful to have an always matching tier). |
| attributes.**price_amount_cents** | `integer` | The price of this price tier, in cents. |
| attributes.**price_amount_float** | `float` | The price of this price tier, float. |
| attributes.**formatted_price_amount** | `string` | The price of this price tier, formatted. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**price** | `object` | The associated price. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

