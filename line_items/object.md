---
description: A comprehensive list of the line item resource's attributes and relationships.
---

# The line item object

A line item object is returned as part of the response body of each successful list, retrieve, create or update API call <b>to the /api/line_items endpoint</b>.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `line_items`                        |
| **id**         | `string` | The line item unique identifier  |
| links.**self** | `string` | The line item endpoint URL       |
| attributes.**sku_code** | `string` | The code of the associated sku. |
| attributes.**bundle_code** | `string` | The code of the associated bundle. |
| attributes.**quantity** | `integer` | The line item quantity. |
| attributes.**_external_price** | `boolean, value is 'false'` | When creating a new line item, set this attribute to '1' if you want to inject the unit_amount_cents price from an external source. |
| attributes.**_update_quantity** | `boolean, value is 'true'` | When creating a new line item, set this attribute to '1' if you want to update the line item quantity (if present) instead of creating a new line item for the same sku. |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard, automatically inherited from the order's market. |
| attributes.**unit_amount_cents** | `integer` | The unit amount of the line item, in cents. Can be specified without an item, otherwise is automatically populated from the price list associated to the order's market. |
| attributes.**unit_amount_float** | `float` | The unit amount of the line item, float. This can be useful to track the purchase on thrid party systems, e.g Google Analyitcs Enhanced Ecommerce. |
| attributes.**formatted_unit_amount** | `string` | The unit amount of the line item, formatted. This can be useful to display the amount with currency in you views. |
| attributes.**options_amount_cents** | `integer` | The options amount of the line item, in cents. |
| attributes.**options_amount_float** | `float` | The options amount of the line item, float. |
| attributes.**formatted_options_amount** | `string` | The options amount of the line item, formatted. |
| attributes.**discount_cents** | `integer` | The discount applied to the line item, in cents. When you apply a discount to an order, this is automatically calculated basing on the line item total_amount_cents value. |
| attributes.**discount_float** | `float` | The discount applied to the line item, float. When you apply a discount to an order, this is automatically calculated basing on the line item total_amount_cents value. |
| attributes.**formatted_discount** | `string` | The discount applied to the line item, fromatted. When you apply a discount to an order, this is automatically calculated basing on the line item total_amount_cents value. |
| attributes.**total_amount_cents** | `integer` | Calculated as unit amount x quantity + options amount, in cents. |
| attributes.**total_amount_float** | `float` | Calculated as unit amount x quantity + options amount, float. This can be useful to track the purchase on thrid party systems, e.g Google Analyitcs Enhanced Ecommerce. |
| attributes.**formatted_total_amount** | `string` | Calculated as unit amount x quantity + options amount, formatted. This can be useful to display the amount with currency in you views. |
| attributes.**tax_amount_cents** | `integer` | Calculated as total amount cents - discount cent * tax rate, in cents. |
| attributes.**tax_amount_float** | `float` | Calculated as total amount cents - discount cent * tax rate, float. |
| attributes.**formatted_tax_amount** | `string` | Calculated as total amount cents - discount cent * tax rate, formatted. |
| attributes.**name** | `string` | The name of the line item. When blank, it gets populated with the name of the associated item (if present). |
| attributes.**image_url** | `string` | The image_url of the line item. When blank, it gets populated with the image_url of the associated item (if present, sku only). |
| attributes.**discount_breakdown** | `object` | The discount breakdown for this line item (if calculated). |
| attributes.**tax_rate** | `float` | The tax rate for this line item (if calculated). |
| attributes.**tax_breakdown** | `object` | The tax breakdown for this line item (if calculated). |
| attributes.**item_type** | `string` | The type of the associate item. Can be one of 'sku', 'bundle', 'shipment', 'payment_method', 'adjustment', 'gift_card', or a valid promotion type. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**order** | `object` | The associated order. |
| relationships.**item** | `object` | The polymorphic item associated to the line item. Can be a 'sku', a 'shipment', a 'payment_method', an 'adjustment', a 'gift_card', or a valid promotion type. |
| relationships.**line_item_options** | `array` | The associated line item options. |
| relationships.**shipment_line_items** | `array` | The associated shipment line items. |
| relationships.**stock_line_items** | `array` | The associated stock line items. |
| relationships.**stock_transfers** | `array` | The associated stock transfers. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

