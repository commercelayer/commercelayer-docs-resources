---
description: An **adjustment** object is returned as part of the response body of each successful list, retrieve, create or update API call.
---

# The adjustment object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `adjustments`                        |
| **id**         | `string` | The adjustment unique identifier  |
| links.**self** | `string` | The adjustment endpoint URL       |
| attributes.**name** | `string` | The adjustment name |
| attributes.**currency_code** | `string` | The international 3-letter currency code as defined by the ISO 4217 standard. |
| attributes.**amount_cents** | `integer` | The adjustment amount, in cents. |
| attributes.**amount_float** | `float` | The adjustment amount, float. |
| attributes.**formatted_amount** | `string` | The adjustment amount, formatted. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

