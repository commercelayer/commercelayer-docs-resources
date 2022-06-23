---
description: >-
  The event object and the allowed CRUD operations on the related resource
  endpoint
---

# Events

Events are automatically created for a resource when a specific action happens (i.e. `orders.place`). When a [webhook](../webhooks/) is listening to that action's topic and the subscribed event occurs, Commerce Layer sends a `POST` request to the webhook's callback URL, and the associated [event callback](../event\_callbacks/) is created.

Events can be [included](https://docs.commercelayer.io/developers/including-associations) when fetching the resources that support them to inspect each recorded action.

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/real-time-webhooks) for more info about real-time webhooks and the related events.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of events or a specific single one.
{% endhint %}
