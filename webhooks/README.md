---
description: >-
  The webhook object and the allowed CRUD operations on the related resource
  endpoint
---

# Webhooks

Webhooks are used to send real-time [events](../events/) to external listeners.

When a webhook is triggered, Commerce Layer sends a `POST` request to the webhook's `callback_url` and the related [event callback](../event\_callbacks/) is created. The request contains a JSON payload in the same format that you get when fetching the same resource through the REST API. For each resource, you can also configure the related resources that should be [included](https://docs.commercelayer.io/developers/including-associations) in the request body (listed in the `include_resources` attribute).

{% hint style="info" %}
The endpoint listening for webhooks has **5 seconds** to respond with a **`2xx`** (usually `200` ) response code, acknowledging a successful delivery. If the request times out or gets a response with a status code other than `2xx`, it is considered failed.
{% endhint %}

Each webhook has a `circuit_state` breaker (`closed` by default) that can become `open` once the number of consecutive failures exceeds the [specified threshold](https://docs.commercelayer.io/developers/real-time-webhooks#handling-webhook-failures), in such case no further calls to the failing callback are made. You can check the number of consecutive failures recorded by the circuit breaker associated with a webhook by inspecting the `circuit_failure_count` attribute. The counter will be reset on the first successful call to the callback URL. You can force the circuit's reset (to the `closed` state and zero failures count) by updating the webhook with the trigger attribute `_reset_circuit` set to `true`.

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/real-time-webhooks) for more info about real-time webhooks and the related events.

</details>
