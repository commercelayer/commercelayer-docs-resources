---
description: A comprehensive list of the stock line item resource's attributes and relationships.
---

# The stock line item object

A stock line item object is returned as part of the response body of each successful list or retrieve API call to the `/api/stock_line_items` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `stock_line_items`                        |
| **id**         | `string` | The stock line item unique identifier  |
| links.**self** | `string` | The stock line item endpoint URL       |
| attributes.**sku_code** | `string` | The code of the associated sku. |
| attributes.**bundle_code** | `string` | The code of the associated bundle. |
| attributes.**quantity** | `integer` | The line item quantity. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**shipment** | `object` | The associated shipment. |
| relationships.**line_item** | `object` | The associated line item. |
| relationships.**stock_item** | `object` | The associated stock item. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

