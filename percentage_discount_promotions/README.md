---
description: >-
  The percentage discount promotion object and the allowed CRUD operations on
  the related resource endpoint
---

# Percentage discount promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion\_rules).

When triggered, percentage discount promotions are responsible for adding a specific percentage discount to the subtotal amount of the orders involved.

Within the time window given by their activation and expiration dates, percentage discount promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active percentage discount promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope, if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.

{% hint style="info" %}
If a percentage discount promotion is associated with an [SKU list](https://docs.commercelayer.io/api/resources/sku\_lists), the related discount is calculated on the SKUs belonging to that list only.
{% endhint %}
