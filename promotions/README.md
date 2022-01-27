---
description: >-
  The promotion object and the allowed CRUD operations on the related resource
  endpoint
---

# Promotions

Commerce Layer provides a promotional engine built on top of two main resources: promotions and [promotion rules](../promotion\_rules/).

Promotions are defined by currency code and can be restricted to a specific market (in the latter case the currency code is inherited by the market's price list). When triggered, promotions are responsible for adding a discount (based on the promotion type) to the orders involved. Within the time window given by their activation and expiration dates, promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope if the promotion is attached to a market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.

{% hint style="info" %}
The number of promotions that can be activated for a single market is subject to limitations: by default, only **a maximum of 10 active promotions per market** is allowed, regardless of their type (limit may vary depending on your plan).
{% endhint %}

At the moment [fixed amount](../fixed\_amount\_promotions/), [fixed price](../fixed\_price\_promotions/), [free shipping](../free\_shipping\_promotions/), [free gift](../free\_gift\_promotions/), and [percentage discount](../percentage\_discount\_promotions/) are available (more to come). For any other cases, evaluate the option to leverage [external promotions](../external\_promotions/).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/promotions-and-gift-cards) and explore the flowchart that illustrates how the promotion resource relates to the other API entities.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of promotions or a specific single one.
{% endhint %}
