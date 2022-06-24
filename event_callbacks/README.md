---
description: >-
  The event callback object and the allowed CRUD operations on the related
  resource endpoint
---

# Event callbacks

Event callbacks are created automatically as responses to the call to a [webhook](../webhooks/) callback URL. You can read the payload sent and check the response status code.&#x20;

{% hint style="info" %}
Events callbacks are retained in our database **for one month only**.
{% endhint %}

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/real-time-webhooks) for more info about real-time webhooks and webhooks callbacks.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of event callbacks or a specific single one.
{% endhint %}
