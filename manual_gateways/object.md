---
description: A comprehensive list of the manual gateway resource's attributes and relationships
---

# The manual gateway object

A manual gateway object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/manual_gateways` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `manual_gateways`                        |
| **id**         | `string` | The manual gateway unique identifier  |
| links.**self** | `string` | The manual gateway endpoint URL       |
| attributes.**name** | `string` | The payment gateway's internal name. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| attributes.**require_capture** | `boolean` | Indicates if the gateway requires to captured. |
| relationships.**payment_methods** | `array` | The associated payment methods. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

