---
description: The promotion object and its fields
---

# Promotions

Commerce Layer provides a promotional engine built on top of two main resources: promotions and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Promotions are defined by market and — when triggered — are responsible for adding a specific discount to the market orders, based on their type. Within the time window given by their activation and expiration dates, promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active promotion, the related discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them. 

At the moment [fixed amount](https://docs.commercelayer.io/api/resources/fixed_amount_promotions), [free shipping](https://docs.commercelayer.io/api/resources/free_shipping_promotions), and [percentage discount](https://docs.commercelayer.io/api/resources/percentage_discount_promotions) are available (more to come). For any other cases, evaluate the option to leverage [external promotions](https://docs.commercelayer.io/api/resources/external_promotions).

The number of promotions that can be activated for a single market is subject to limitations: only **a maximum of 10 active promotions per market** is allowed, regardless of their type.