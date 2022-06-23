---
description: A comprehensive list of the SKU resource's attributes and relationships
---

# The SKU object

A SKU object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/skus` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `skus`                        |
| **id**         | `string` | The SKU unique identifier  |
| links.**self** | `string` | The SKU endpoint URL       |
| attributes.**code** | `string` | The SKU code, that uniquely identifies the SKU within the organization. |
| attributes.**name** | `string` | The internal name of the SKU. |
| attributes.**description** | `string` | An internal description of the SKU. |
| attributes.**image_url** | `string` | The URL of an image that represents the SKU. |
| attributes.**pieces_per_pack** | `integer` | The number of pieces that compose the SKU. This is useful to describe sets and bundles. |
| attributes.**weight** | `float` | The weight of the SKU. If present, it will be used to calculate the shipping rates. |
| attributes.**unit_of_weight** | `string` | Can be one of 'gr', 'lb', or 'oz' |
| attributes.**hs_tariff_number** | `string` | The Harmonized System Code used by customs to identify the products shipped across international borders. |
| attributes.**do_not_ship** | `boolean` | Indicates if the SKU doesn't generate shipments. |
| attributes.**do_not_track** | `boolean` | Indicates if the SKU doesn't track the stock inventory. |
| attributes.**inventory** | `object` | Aggregated information about the SKU's inventory. Returned only when retrieving a single SKU. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**shipping_category** | `object` | The SKU's shipping category |
| relationships.**prices** | `array` | The list of prices associated with the SKU. |
| relationships.**stock_items** | `array` | The list of stock items associated with the SKU. |
| relationships.**delivery_lead_times** | `array` | The list of delivery lead times associated with the SKU. |
| relationships.**sku_options** | `array` | The list of SKU options available for the SKU. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

