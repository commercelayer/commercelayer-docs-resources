---
description: >-
  The promotion rule object and the allowed CRUD operations on the related
  resource endpoint
---

# Promotion rules

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and promotion rules.

If one or more promotion rules are defined, the promotion is triggered only when it matches all of them. Otherwise, if no promotion rule is associated with an active promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope if the promotion is restricted to a specific market).

At the moment [order amount](../order\_amount\_promotion\_rules/), [SKU list](../sku\_list\_promotion\_rules/), and [coupon code](../coupon\_codes\_promotion\_rules/) promotion rules are available (more to come).

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of promotion rules or a specific single one.
{% endhint %}
