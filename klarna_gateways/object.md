---
description: A comprehensive list of the klarna gateway resource's attributes and relationships
---

# The klarna gateway object

A klarna gateway object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/klarna_gateways` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `klarna_gateways`                        |
| **id**         | `string` | The klarna gateway unique identifier  |
| links.**self** | `string` | The klarna gateway endpoint URL       |
| attributes.**name** | `string` | The payment gateway's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**country_code** | `string` | The gateway country code one of EU, US, or OC. |
| attributes.**api_key** | `string` | The public key linked to your API credential. |
| attributes.**api_secret** | `string` | The gateway API key. |
| relationships.**payment_methods** | `array` | The associated payment methods. |
| relationships.**klarna_payments** | `array` | The associated payments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

