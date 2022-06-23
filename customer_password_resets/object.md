---
description: A comprehensive list of the customer password reset resource's attributes and relationships
---

# The customer password reset object

A customer password reset object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/customer_password_resets` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `customer_password_resets`                        |
| **id**         | `string` | The customer password reset unique identifier  |
| links.**self** | `string` | The customer password reset endpoint URL       |
| attributes.**customer_email** | `string` | The email of the customer that requires a password reset |
| attributes.**reset_password_token** | `string` | Automatically generated on create. Send its value as the '_reset_password_token' argument when updating the customer password. |
| attributes.**customer_password** | `string` | The customer new password. This will be accepted only if a valid '_reset_password_token' is sent with the request. |
| attributes.**_reset_password_token** | `string` | Send the 'reset_password_token' that you got on create when updating the customer password. |
| attributes.**reset_password_at** | `datetime` | Time at which the password was reset. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**customer** | `object` | The customer that requires a password reset. |
| relationships.**events** | `array` | The associated events. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

