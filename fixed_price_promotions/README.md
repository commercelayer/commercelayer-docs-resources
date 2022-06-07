---
description: >-
  The fixed price promotion object and the allowed CRUD operations on the
  related resource endpoint
---

# Fixed price promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

When triggered, fixed price promotions are responsible for adding a discount to the orders involved. The discount amount is computed by imposing a fixed price for the SKUs matching the associated list.

Within the time window given by their activation and expiration dates, fixed price promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active fixed price promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.

{% hint style="info" %}
In order for a fixed price promotion to apply to [bundles](../bundles/), the resources must share the same [SKU list](../sku\_lists/). Fixed price promotions can be combined with other promotion types, but cannot overlap with [free gift promotions](../free\_gift\_promotions/) (which have a higher priority) or with other active fixed price promotions (the first which applies has precedence).
{% endhint %}
