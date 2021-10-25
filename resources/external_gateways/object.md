---
description: An **external gateway** object is returned as part of the response body of each successful list, retrieve, create or update API call.
---

# The external gateway object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `external_gateways`                        |
| **id**         | `string` | The external gateway unique identifier  |
| links.**self** | `string` | The external gateway endpoint URL       |
| attributes.**name** | `string` | The payment gateway's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**shared_secret** | `string` | The shared secret used to sign gateway payloads. |
| attributes.**authorize_url** | `string` | The endpoint used by the external gateway to authorize payments. |
| attributes.**capture_url** | `string` | The endpoint used by the external gateway to capture payments. |
| attributes.**void_url** | `string` | The endpoint used by the external gateway to void payments. |
| attributes.**refund_url** | `string` | The endpoint used by the external gateway to refund payments. |
| relationships.**payment_methods** | `array` | The associated payment methods. |
| relationships.**external_payments** | `array` | The associated payments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

