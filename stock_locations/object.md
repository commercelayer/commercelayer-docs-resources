---
description: A comprehensive list of the stock location resource's attributes and relationships.
---

# The stock location object

A stock location object is returned as part of the response body of each successful list, retrieve, create or update API call <b>to the /api/stock_locations endpoint</b>.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `stock_locations`                        |
| **id**         | `string` | The stock location unique identifier  |
| links.**self** | `string` | The stock location endpoint URL       |
| attributes.**number** | `integer` | Unique identifier for the stock location (numeric) |
| attributes.**name** | `string` | The stock location's internal name. |
| attributes.**label_format** | `string` | The shipping label format for this stock location. Can be one of 'PDF', 'ZPL', 'EPL2', or 'PNG' |
| attributes.**suppress_etd** | `boolean` | Flag it if you want to skip the electronic invoice creation when generating the customs info for this stock location shipments. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**address** | `object` | The stock location's phisical address, used as the shipping addresses "from" address. |
| relationships.**inventory_stock_locations** | `array` | The inventory stock locations associated to the stock location. |
| relationships.**inventory_return_locations** | `array` | The inventory return locations associated to the stock location. |
| relationships.**stock_items** | `array` | The items stocked in this location. |
| relationships.**stock_transfers** | `array` | The stock transfers associated to the stock location. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

