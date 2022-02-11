---
description: A comprehensive list of the paypal gateway resource's attributes and relationships
---

# The paypal gateway object

A paypal gateway object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/paypal_gateways` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `paypal_gateways`                        |
| **id**         | `string` | The paypal gateway unique identifier  |
| links.**self** | `string` | The paypal gateway endpoint URL       |
| attributes.**name** | `string` | The payment gateway's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**client_id** | `string` | The gateway client ID. |
| attributes.**client_secret** | `string` | The gateway client secret. |
| relationships.**payment_methods** | `array` | The associated payment methods. |
| relationships.**paypal_payments** | `array` | The associated payments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

