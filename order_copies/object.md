---
description: A comprehensive list of the order copy resource's attributes and relationships.
---

# The order copy object

An order copy object is returned as part of the response body of each successful list, retrieve or create API call.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `order_copies`                        |
| **id**         | `string` | The order copy unique identifier  |
| links.**self** | `string` | The order copy endpoint URL       |
| attributes.**status** | `string` | The order copy status. One of 'pending' (default), 'in_progress', 'failed', or 'completed'. |
| attributes.**started_at** | `datetime` | Time at which the order copy was started. |
| attributes.**completed_at** | `datetime` | Time at which the order copy was completed. |
| attributes.**failed_at** | `datetime` | Time at which the order copy has failed. |
| attributes.**place_target_order** | `boolean` | Indicates if the target order must be placed upon copy. |
| attributes.**cancel_source_order** | `boolean` | Indicates if the source order must be cancelled upon copy. |
| attributes.**reuse_wallet** | `boolean` | Indicates if the payment source within the source order customer's wallet must be copied. |
| attributes.**errors_log** | `object` | Contains the order copy errors, if any. |
| attributes.**errors_count** | `integer` | Indicates the number of copy errors, if any. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**source_order** | `object` | The source order to copy from. |
| relationships.**target_order** | `object` | The copied target order. |
| relationships.**order_subscription** | `object` | The associated order subscription. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

