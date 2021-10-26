---
description: The fixed amount promotion object and its fields
---

# Fixed amount promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Fixed amount promotions are defined by market and — when triggered — are responsible for adding a fixed amount discount to the market orders. Within the time window given by their activation and expiration dates, fixed amount promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active fixed amount promotion, the related discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.
