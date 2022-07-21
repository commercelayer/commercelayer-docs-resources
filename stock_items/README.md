---
description: >-
  The stock item object and the allowed CRUD operations on the related resource
  endpoint
---

# Stock items

A stock item keeps the available inventory of an [SKU](../skus/) in a given [stock location](../stock\_locations/).&#x20;

{% hint style="info" %}
When you create a line item, the associated SKU must be available in one of the market's stock locations.
{% endhint %}

When you place an [order](../orders/), the stock item quantities get decremented. When an order is [cancelled](../voids/), or a [return](../returns/) is approved, the stock item quantities get incremented.
