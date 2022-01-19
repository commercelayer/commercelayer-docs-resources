---
description: A comprehensive list of the SKU list promotion rule resource's attributes and relationships
---

# The SKU list promotion rule object

A SKU list promotion rule object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/sku_list_promotion_rules` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `sku_list_promotion_rules`                        |
| **id**         | `string` | The SKU list promotion rule unique identifier  |
| links.**self** | `string` | The SKU list promotion rule endpoint URL       |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**all_skus** | `boolean` | Indicates if the rule is activated only when all of the SKUs of the list is also part of the order. |
| attributes.**min_quantity** | `integer` | The min quantity of SKUs of the list that must be also part of the order. If positive, overwrites the 'all_skus' option. When the sku_list is manual, its items quantities are honoured. |
| relationships.**promotion** | `object` | The associated promotion. |
| relationships.**sku_list** | `object` | The associated sku_list. |
| relationships.**skus** | `array` | The associated SKUs. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

