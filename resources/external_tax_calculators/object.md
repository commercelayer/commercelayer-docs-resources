---
description: An **external tax calculator** object is returned as part of the response body of each successful list, retrieve, create or update API call.
---

# The external tax calculator object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `external_tax_calculators`                        |
| **id**         | `string` | The external tax calculator unique identifier  |
| links.**self** | `string` | The external tax calculator endpoint URL       |
| attributes.**name** | `string` | The tax calculator's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**tax_calculator_url** | `string` | The URL to the service that will compute the taxes. |
| relationships.**tax_categories** | `array` | The associated tax categories. |
| relationships.**markets** | `array` | The associated markets. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

