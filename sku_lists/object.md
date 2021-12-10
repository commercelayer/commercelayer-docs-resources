---
description: A comprehensive list of the SKU list resource's attributes and relationships.
---

# The SKU list object

A SKU list object is returned as part of the response body of each successful list, retrieve, create or update API call <b>to the /api/sku_lists endpoint</b>.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `sku_lists`                        |
| **id**         | `string` | The SKU list unique identifier  |
| links.**self** | `string` | The SKU list endpoint URL       |
| attributes.**name** | `string` | The SKU list's internal name. |
| attributes.**slug** | `string` | The SKU list's internal slug. |
| attributes.**description** | `string` | An internal description of the SKU list. |
| attributes.**image_url** | `string` | The URL of an image that represents the SKU list. |
| attributes.**manual** | `boolean` | Indicates if the SKU list is populated manually. |
| attributes.**sku_code_regex** | `string` | The regex that will be evaluated to match the SKU codes. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**skus** | `array` | The associated SKUs. |
| relationships.**sku_list_items** | `array` | The associated SKU list items. |
| relationships.**bundles** | `array` | The associated bundles. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

