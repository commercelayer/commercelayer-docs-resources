---
description: A comprehensive list of the fixed amount promotion resource's attributes and relationships
---

# The fixed amount promotion object

A fixed amount promotion object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/fixed_amount_promotions` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `fixed_amount_promotions`                        |
| **id**         | `string` | The fixed amount promotion unique identifier  |
| links.**self** | `string` | The fixed amount promotion endpoint URL       |
| attributes.**name** | `string` | The promotion's internal name. |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard. |
| attributes.**starts_at** | `datetime` | The activation date/time of this promotion. |
| attributes.**expires_at** | `datetime` | The expiration date/time of this promotion (must be after starts_at). |
| attributes.**total_usage_limit** | `integer` | The total number of times this promotion can be applied. |
| attributes.**total_usage_count** | `integer` | The number of times this promotion has been applied. |
| attributes.**active** | `boolean` | Indicates if the promotion is active. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**fixed_amount_cents** | `integer` | The discount fixed amount to be applied, in cents |
| attributes.**fixed_amount_float** | `float` | The discount fixed amount to be applied, float. |
| attributes.**formatted_fixed_amount** | `string` | The discount fixed amount to be applied, formatted. |
| attributes.**events** | `has_many` | The associated events. |
| relationships.**market** | `object` | The associated market. |
| relationships.**promotion_rules** | `array` | The associated promotion rules. |
| relationships.**order_amount_promotion_rule** | `object` | The associated order amount promotion rule. |
| relationships.**sku_list_promotion_rule** | `object` | The associated SKU list promotion rule. |
| relationships.**coupon_codes_promotion_rule** | `object` | The associated coupon codes promotion rule. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

