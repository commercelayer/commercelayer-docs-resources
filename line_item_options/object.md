---
description: A comprehensive list of the line item option resource's attributes and relationships.
---

# The line item option object

A line item option object is returned as part of the response body of each successful list, retrieve, create or update API call.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `line_item_options`                        |
| **id**         | `string` | The line item option unique identifier  |
| links.**self** | `string` | The line item option endpoint URL       |
| attributes.**name** | `string` | The name of the line item option. When blank, it gets populated with the name of the associated sku option. |
| attributes.**quantity** | `integer` | The line item option's quantity |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard, automatically inherited from the order's market. |
| attributes.**unit_amount_cents** | `integer` | The unit amount of the line item option, in cents. When you add a line item option to an order, this is automatically populated from associated sku option's price. |
| attributes.**unit_amount_float** | `float` | The unit amount of the line item option, float. This can be useful to track the purchase on thrid party systems, e.g Google Analyitcs Enhanced Ecommerce. |
| attributes.**formatted_unit_amount** | `string` | The unit amount of the line item option, formatted. This can be useful to display the amount with currency in you views. |
| attributes.**total_amount_cents** | `integer` | The unit amount x quantity, in cents. |
| attributes.**total_amount_float** | `float` | The unit amount x quantity, float. This can be useful to track the purchase on thrid party systems, e.g Google Analyitcs Enhanced Ecommerce. |
| attributes.**formatted_total_amount** | `string` | The unit amount x quantity, formatted. This can be useful to display the amount with currency in you views. |
| attributes.**delay_hours** | `integer` | The shipping delay that the customer can expect when adding this option (hours). Inherited from the associated sku option. |
| attributes.**delay_days** | `integer` | The shipping delay that the customer can expect when adding this option (days, rounded). |
| attributes.**options** | `object` | Set of key-value pairs that represent the selected options. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**line_item** | `object` | The associated line item. |
| relationships.**sku_option** | `object` | The associated sku option. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

