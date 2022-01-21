---
description: >-
  The free shipping promotion object and the allowed CRUD operations on the
  related resource endpoint
---

# Free shipping promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

When triggered, free shipping promotions are responsible for setting to zero the shipping amount of the orders involved.

Within the time window given by their activation and expiration dates, free shipping promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active free shipping promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope, if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.
