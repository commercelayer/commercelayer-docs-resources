---
description: >-
  The price object and the allowed CRUD operations on the related resource
  endpoint
---

# Prices

[SKUs](../skus/) can have a price for each [price list](../price\_lists/). When you create a [line item](../line\_items/), it gets the price associated with the order's price list.

{% hint style="info" %}
Some currencies have a zero exponent and cannot be expressed **in cents** (e.g. `JPY` and `HUF`). In such cases, you have to express the value as it is (e.g. `10000` JPY, not `1000000` JPY).
{% endhint %}
