---
description: >-
  The fixed amount promotion object and the allowed CRUD operations on the
  related resource endpoint
---

# Fixed amount promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

When triggered, fixed amount promotions are responsible for adding a fixed amount discount to the orders involved.

Within the time window given by their activation and expiration dates, fixed amount promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active fixed amount promotion, the related discount is applied to all the orders in the specified currency (or to all the orders of the market in scope if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.
