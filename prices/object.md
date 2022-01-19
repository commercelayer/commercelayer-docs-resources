---
description: A comprehensive list of the price resource's attributes and relationships
---

# The price object

A price object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/prices` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `prices`                        |
| **id**         | `string` | The price unique identifier  |
| links.**self** | `string` | The price endpoint URL       |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard, inherited from the associated price list. |
| attributes.**sku_code** | `string` | The code of the associated SKU. When creating a price, either a valid sku_code or a SKU relationship must be present. |
| attributes.**amount_cents** | `integer` | The SKU price amount for the associated price list, in cents. |
| attributes.**amount_float** | `float` | The SKU price amount for the associated price list, float. |
| attributes.**formatted_amount** | `string` | The SKU price amount for the associated price list, formatted. |
| attributes.**compare_at_amount_cents** | `integer` | The compared price amount, in cents. Useful to display a percentage discount. |
| attributes.**compare_at_amount_float** | `float` | The compared price amount, float. |
| attributes.**formatted_compare_at_amount** | `string` | The compared price amount, formatted. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**price_list** | `object` | The associated price list. |
| relationships.**sku** | `object` | The associated SKU. When creating a price, either a SKU relationship or a valid sku_code must be present. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

