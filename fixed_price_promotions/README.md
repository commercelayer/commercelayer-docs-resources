---
description: The fixed price promotion object and its fields
---

# Fixed price promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Fixed price promotions are defined by market and — when triggered — are responsible for adding a discount to the market orders. The discount amount is computed imposing a fixed price for the SKUs matching the associated list. Within the time window given by their activation and expiration dates, fixed price promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active fixed price promotion, the related discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them. Fixed price promotions do not apply to [bundles](https://docs.commercelayer.io/api/resources/bundles) and cannot be combined with other promotions of the same type, or with [free gift promotions](https://docs.commercelayer.io/api/resources/free_gift_promotions) (which have a higher priority).


