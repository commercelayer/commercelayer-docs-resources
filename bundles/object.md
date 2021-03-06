---
description: A comprehensive list of the bundle resource's attributes and relationships
---

# The bundle object

A bundle object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/bundles` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `bundles`                        |
| **id**         | `string` | The bundle unique identifier  |
| links.**self** | `string` | The bundle endpoint URL       |
| attributes.**code** | `string` | The bundle code, that uniquely identifies the bundle within the market. |
| attributes.**name** | `string` | The internal name of the bundle. |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard. |
| attributes.**description** | `string` | An internal description of the bundle. |
| attributes.**image_url** | `string` | The URL of an image that represents the bundle. |
| attributes.**do_not_ship** | `boolean` | Indicates if the bundle doesn't generate shipments. |
| attributes.**do_not_track** | `boolean` | Indicates if the bundle doesn't track the stock inventory. |
| attributes.**price_amount_cents** | `integer` | The bundle price amount for the associated market, in cents. |
| attributes.**price_amount_float** | `float` | The bundle price amount for the associated market, float. |
| attributes.**formatted_price_amount** | `string` | The bundle price amount for the associated market, formatted. |
| attributes.**compare_at_amount_cents** | `integer` | The compared price amount, in cents. Useful to display a percentage discount. |
| attributes.**compare_at_amount_float** | `float` | The compared price amount, float. |
| attributes.**formatted_compare_at_amount** | `string` | The compared price amount, formatted. |
| attributes.**_compute_price_amount** | `boolean, value is 'true'` | Send this attribute if you want to compute the price_amount_cents as the sum of the prices of the bundle SKUs for the market. |
| attributes.**_compute_compare_at_amount** | `boolean, value is 'true'` | Send this attribute if you want to compute the compare_at_amount_cents as the sum of the prices of the bundle SKUs for the market. |
| attributes.**skus_count** | `integer` | The total number of SKUs in the bundle. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**market** | `object` | The associated market. |
| relationships.**sku_list** | `object` | The associated SKU list. |
| relationships.**skus** | `array` | The associated SKUs. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

