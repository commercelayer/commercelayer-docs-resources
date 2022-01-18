---
description: >-
  The promotion object and the allowed CRUD operations on the related resource
  endpoint
---

# Promotions

Commerce Layer provides a promotional engine built on top of two main resources: promotions and [promotion rules](https://docs.commercelayer.io/api/resources/promotion\_rules). Promotions can be defined by market and — when triggered — are responsible for adding a specific discount to the market orders, based on their type. Within the time window given by their activation and expiration dates, promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active promotion, the related discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.

At the moment [fixed amount](https://docs.commercelayer.io/api/resources/fixed\_amount\_promotions), [free shipping](https://docs.commercelayer.io/api/resources/free\_shipping\_promotions), and [percentage discount](https://docs.commercelayer.io/api/resources/percentage\_discount\_promotions) are available (more to come). For any other cases, evaluate the option to leverage [external promotions](https://docs.commercelayer.io/api/resources/external\_promotions).

The number of promotions that can be activated for a single market is subject to limitations: only **a maximum of 10 active promotions per market** is allowed, regardless of their type.
