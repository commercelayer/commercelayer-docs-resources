---
description: A comprehensive list of the stock transfer resource's attributes and relationships.
---

# The stock transfer object

A stock transfer object is returned as part of the response body of each successful list, retrieve, create or update API call <b>to the /api/stock_transfers endpoint</b>.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `stock_transfers`                        |
| **id**         | `string` | The stock transfer unique identifier  |
| links.**self** | `string` | The stock transfer endpoint URL       |
| attributes.**sku_code** | `string` | The code of the associated sku. |
| attributes.**status** | `string` | The stock transfer status, one of 'draft', 'upcoming', 'picking', 'in_transit', 'completed', or 'cancelled' |
| attributes.**quantity** | `integer` | The stock quantity to be transferred from the origin stock location to destination one |
| attributes.**completed_at** | `datetime` | Time at which the stock transfer was completed. |
| attributes.**cancelled_at** | `datetime` | Time at which the stock transfer was cancelled. |
| attributes.**_upcoming** | `boolean, value is 'true'` | Send this attribute if you want to mark this stock transfer as upcoming. |
| attributes.**_picking** | `boolean, value is 'true'` | Send this attribute if you want to start picking this stock transfer. |
| attributes.**_in_transit** | `boolean, value is 'true'` | Send this attribute if you want to mark this stock transfer as in transit. |
| attributes.**_complete** | `boolean, value is 'true'` | Send this attribute if you want to complete this stock transfer. |
| attributes.**_cancel** | `boolean, value is 'true'` | Send this attribute if you want to cancel this stock transfer. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**sku** | `object` | The associated sku. |
| relationships.**origin_stock_location** | `object` | The origin stock location. |
| relationships.**destination_stock_location** | `object` | The destination stock location. |
| relationships.**shipment** | `object` | The associated shipment. |
| relationships.**line_item** | `object` | The associated line_item. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

