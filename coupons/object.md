---
description: A comprehensive list of the coupon resource's attributes and relationships.
---

# The coupon object

A coupon object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/coupons` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `coupons`                        |
| **id**         | `string` | The coupon unique identifier  |
| links.**self** | `string` | The coupon endpoint URL       |
| attributes.**code** | `string` | The coupon code, that uniquely identifies the coupon within the promotion rule. |
| attributes.**customer_single_use** | `boolean` | Indicates if the coupon can be used just once per customer. |
| attributes.**usage_limit** | `integer` | The total number of times this coupon can be used. |
| attributes.**usage_count** | `integer` | The number of times this coupon has been used. |
| attributes.**recipient_email** | `string` | The email address of the associated recipient. When creating or updating a coupon, this is a shortcut to find or create the associated recipient by email. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**promotion_rule** | `object` | The associated promotion rule. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

