---
description: An import object is returned as part of the response body of each successful list, retrieve or create API call.
---

# The import object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `imports`                        |
| **id**         | `string` | The import unique identifier  |
| links.**self** | `string` | The import endpoint URL       |
| attributes.**resource_type** | `string` | The type of resource being imported. |
| attributes.**parent_resource_id** | `string` | The ID of the parent resource to be associated with imported data. |
| attributes.**status** | `string` | The import job status. One of 'pending' (default), 'in_progress', 'interrputed', or 'completed'. |
| attributes.**started_at** | `datetime` | Time at which the import was started. |
| attributes.**completed_at** | `datetime` | Time at which the import was completed. |
| attributes.**interrupted_at** | `datetime` | Time at which the import was interrupted. |
| attributes.**inputs** | `array` | Array of objects representing the resources that are being imported. |
| attributes.**inputs_size** | `integer` | Indicates the size of the objects to be imported. |
| attributes.**errors_count** | `integer` | Indicates the number of import errors, if any. |
| attributes.**warnings_count** | `integer` | Indicates the number of import warnings, if any. |
| attributes.**destroyed_count** | `integer` | Indicates the number of records that have been destroyed, if any. |
| attributes.**processed_count** | `integer` | Indicates the number of records that have been processed (created or updated). |
| attributes.**errors_log** | `object` | Contains the import errors, if any. |
| attributes.**warnings_log** | `object` | Contains the import warnings, if any. |
| attributes.**cleanup_records** | `boolean` | Indicates if the import should cleanup records that are not included in the inputs array. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

