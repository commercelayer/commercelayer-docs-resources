---
description: A comprehensive list of the klarna payment resource's attributes and relationships.
---

# The klarna payment object

A klarna payment object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/klarna_payments` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `klarna_payments`                        |
| **id**         | `string` | The klarna payment unique identifier  |
| links.**self** | `string` | The klarna payment endpoint URL       |
| attributes.**session_id** | `string` | The identifier of the payment session, useful to updated it. |
| attributes.**client_token** | `string` | The public token linked to your API credential. Available upon session creation. |
| attributes.**payment_methods** | `array` | The merchant available payment methods for the assoiated order. Available upon session creation. |
| attributes.**auth_token** | `string` | The token returned by a successful client authorization, mandatory to place the order. |
| attributes.**_update** | `boolean, value is 'true'` | Send this attribute if you want to update the payment session with fresh order data. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**order** | `object` | The order associated to the adyen payment, that is set as its payment source. |
| relationships.**payment_gateway** | `object` | The associated payment gateway, inherited by the order payment_method. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

