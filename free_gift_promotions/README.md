---
description: >-
  The free gift promotion object and the allowed CRUD operations on the related
  resource endpoint
---

# Free gift promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

When triggered, free gift promotions are responsible for adding a discount to the orders involved. The discount amount is computed by setting to zero the price of the SKUs matching the associated list. Please note that the discount is applied only when an SKU matching the associated list is added to the order. It is possible to limit the free gifts by specifying a `max_quantity` (default to 1), which also honors the quantities and positions of the list items.

Within the time window given by their activation and expiration dates, free gift promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active free gift promotion, the free gift is applied to all the orders in the specified currency (or to all the orders of the market in scope, if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.&#x20;

{% hint style="info" %}
In order for free gift promotion to apply to [bundles](../bundles/), the resources must share the same [SKU list](../sku\_lists/). Free gift promotions can be combined with other promotion types, but cannot overlap with [fixed price promotions](../fixed\_price\_promotions/) (which have a lower priority) or with other active free gift promotions (the first which applies has precedence).
{% endhint %}
