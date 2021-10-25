---
description: A **coupon recipient** object is returned as part of the response body of each successful list, retrieve, create or update API call.
---

# The coupon recipient object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `coupon_recipients`                        |
| **id**         | `string` | The coupon recipient unique identifier  |
| links.**self** | `string` | The coupon recipient endpoint URL       |
| attributes.**email** | `string` | The recipient email address |
| attributes.**first_name** | `string` | The recipient first name |
| attributes.**last_name** | `string` | The recipient last name |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**customer** | `object` | The associated customer. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

