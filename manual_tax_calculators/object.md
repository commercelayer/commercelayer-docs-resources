---
description: A comprehensive list of the manual tax calculator resource's attributes and relationships.
---

# The manual tax calculator object

A manual tax calculator object is returned as part of the response body of each successful list, retrieve, create or update API call.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `manual_tax_calculators`                        |
| **id**         | `string` | The manual tax calculator unique identifier  |
| links.**self** | `string` | The manual tax calculator endpoint URL       |
| attributes.**name** | `string` | The tax calculator's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**tax_categories** | `array` | The associated tax categories. |
| relationships.**markets** | `array` | The associated markets. |
| relationships.**attachments** | `array` | The associated attachments. |
| relationships.**tax_rules** | `array` | The associated tax rules. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

