---
description: A comprehensive list of the geocoder resource's attributes and relationships
---

# The geocoder object

A geocoder object is returned as part of the response body of each successful list or retrieve API call to the `/api/geocoders` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `geocoders`                        |
| **id**         | `string` | The geocoder unique identifier  |
| links.**self** | `string` | The geocoder endpoint URL       |
| attributes.**name** | `string` | The geocoder's internal name |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**addresses** | `array` | The associated addresses. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

