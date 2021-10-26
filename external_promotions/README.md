---
description: The external promotion object and its fields
---

# External promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Besides the promotion types that are supported out-of-the-box Commerce Layer lets you integrate any kind of promotional engine as an external promotion. External promotions are defined by market and are responsible for adding the externally computed discount to the market orders. When an external promotion activates, Commerce Layer triggers a POST request to the promotion URL endpoint, sending the order payload (including its line items) in the request body. The external service response (or error) must match the format described in [this example](https://docs.commercelayer.io/api/external-resources/external-promotions).

Within the time window given by their activation and expiration dates, external promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active external promotion, the computed discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.
