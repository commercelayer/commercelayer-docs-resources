---
description: A comprehensive list of the market resource's attributes and relationships
---

# The market object

A market object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/markets` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `markets`                        |
| **id**         | `string` | The market unique identifier  |
| links.**self** | `string` | The market endpoint URL       |
| attributes.**number** | `integer` | Unique identifier for the market (numeric) |
| attributes.**name** | `string` | The market's internal name |
| attributes.**facebook_pixel_id** | `string` | The Facebook Pixed ID |
| attributes.**checkout_url** | `string` | The checkout URL for this market |
| attributes.**external_prices_url** | `string` | The URL used to fetch prices from an external source |
| attributes.**private** | `boolean` | Indicates if market belongs to a customer_group. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**merchant** | `object` | The associated merchant. |
| relationships.**price_list** | `object` | The associated price list. |
| relationships.**inventory_model** | `object` | The associated inventory model. |
| relationships.**tax_calculator** | `object` | The associated tax calculator. |
| relationships.**customer_group** | `object` | The associated customer group. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

