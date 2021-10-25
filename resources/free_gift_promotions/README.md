---
description: The free gift promotion object and its fields
---

# Free gift promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Free gift promotions are defined by market and — when triggered — are responsible for adding a discount to the market orders. The discount amount is computed by setting to zero the price of the SKUs matching the associated list. Consider the discount is applied only when a SKU matching the associated list is added to the order. It is possible to limit the free gifts by specifying a `max_quantity` (default to 1), which also honours the quantities and positions of the list items. Within the time window given by their activation and expiration dates, free gift promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active free gift promotion, the free gift is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them. Free gift promotions do not apply to [bundles](https://docs.commercelayer.io/api/resources/bundles) and cannot be combined with other promotions of the same type, or with [fixed price promotions](https://docs.commercelayer.io/api/resources/fixed_price_promotions) (which have a lower priority).


