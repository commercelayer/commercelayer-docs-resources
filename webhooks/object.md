---
description: A webhook object is returned as part of the response body of each successful list, retrieve, create or update API call.
---

# The webhook object

| Field          | Type     | Description                                  |
| -------------- | -------- | -------------------------------------------- |
| **type**       | `string` | `webhooks`                        |
| **id**         | `string` | The webhook unique identifier  |
| links.**self** | `string` | The webhook endpoint URL       |
| attributes.**name** | `string` | Unique name for the webhook. |
| attributes.**topic** | `string` | The identifier of the resource/event that will trigger the webhook. |
| attributes.**callback_url** | `string` | URI where the webhook subscription should send the POST request when the event occurs. |
| attributes.**include_resources** | `array` | List of related resources that should be included in the webhook body. |
| attributes.**circuit_state** | `string` | The circuit breaker state, by default it is 'closed'. It can become 'open' once the number of consecutive failures overlaps the specified threshold, in such case no further calls to the failing callback are made. |
| attributes.**circuit_failure_count** | `integer` | The number of consecutive failures recorded by the circuit breaker associated to this webhook, will be reset on first successful call to callback. |
| attributes.**_reset_circuit** | `boolean, value is 'true'` | Send this attribute if you want to reset the circuit breaker associated to this webhook to 'closed' state and zero failures count. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**last_event_callbacks** | `array` | The last associated event callbacks. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

