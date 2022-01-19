---
description: A comprehensive list of the SKU list item resource's attributes and relationships
---

# The SKU list item object

A SKU list item object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/sku_list_items` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `sku_list_items`                        |
| **id**         | `string` | The SKU list item unique identifier  |
| links.**self** | `string` | The SKU list item endpoint URL       |
| attributes.**position** | `integer` | The SKU list item's position. |
| attributes.**sku_code** | `string` | The code of the associated SKU. |
| attributes.**quantity** | `integer` | The SKU quantity for this SKU list item. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**sku_list** | `object` | The associated SKU list. |
| relationships.**sku** | `object` | The associated sku. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

