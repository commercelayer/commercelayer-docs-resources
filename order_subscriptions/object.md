---
description: A comprehensive list of the order subscription resource's attributes and relationships
---

# The order subscription object

An order subscription object is returned as part of the response body of each successful list, retrieve, create or update API call to the `/api/order_subscriptions` endpoint.

## Fields

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `order_subscriptions`                        |
| **id**         | `string` | The order subscription unique identifier  |
| links.**self** | `string` | The order subscription endpoint URL       |
| attributes.**number** | `string` | Unique identifier for the subscription (numeric) |
| attributes.**status** | `string` | The subscription status. One of 'draft' (default), 'inactive', 'active', or 'cancelled'. |
| attributes.**frequency** | `string` | The frequency of the subscription. One of 'hourly', 'daily', 'weekly', 'monthly', 'two-month', 'three-month', 'four-month', 'six-month', or 'yearly'. |
| attributes.**activate_by_source_order** | `boolean` | Indicates if the subscription will be actvated considering the placed source order as its first run, default to true. |
| attributes.**customer_email** | `string` | The email address of the customer, if any, associated to the source order. |
| attributes.**starts_at** | `datetime` | The activation date/time of this subscription. |
| attributes.**expires_at** | `datetime` | The expiration date/time of this subscription (must be after starts_at). |
| attributes.**next_run_at** | `datetime` | The date/time of the subscription next run. |
| attributes.**occurrencies** | `integer` | The number of times this subscription has run. |
| attributes.**errors_count** | `integer` | Indicates the number of subscription errors, if any. |
| attributes.**succeeded_on_last_run** | `boolean` | Indicates if the subscription has succeeded on its last run. |
| attributes.**options** | `object` | The subscription options used to create the order copy (check order_copies for more information). For subscriptions the `place_target_order` is enabled by default, specify custom options to overwrite it. |
| attributes.**_activate** | `boolean, value is 'true'` | Send this attribute if you want to mark this subscription as active. |
| attributes.**_deactivate** | `boolean, value is 'true'` | Send this attribute if you want to mark this subscription as inactive. |
| attributes.**_cancel** | `boolean, value is 'true'` | Send this attribute if you want to mark this subscription as cancelled. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**market** | `object` | The associated market, inherited from the source order if not specified. |
| relationships.**source_order** | `object` | The subscription source order. |
| relationships.**customer** | `object` | The subscription customer. |
| relationships.**order_copies** | `array` | The associated order copies. |
| relationships.**orders** | `array` | The associated copied orders. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

