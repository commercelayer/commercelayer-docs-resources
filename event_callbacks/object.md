---
description: A comprehensive list of the event callback resource's attributes and relationships
---

# The event callback object

An event callback object is returned as part of the response body of each successful list or retrieve API call to the `/api/event_callbacks` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `event_callbacks`                        |
| **id**         | `string` | The event callback unique identifier  |
| links.**self** | `string` | The event callback endpoint URL       |
| attributes.**callback_url** | `string` | The URI of the callback, inherited by the associated webhook. |
| attributes.**signature** | `string` | The callback signature, used to sign the payload. |
| attributes.**payload** | `object` | The payload sent to the callback endpoint, including the event affected resource and the specified includes. |
| attributes.**response_code** | `string` | The HTTP response code of the callback endpoint. |
| attributes.**response_message** | `string` | The HTTP response message of the callback endpoint. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**webhook** | `object` | The associated webhook. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

