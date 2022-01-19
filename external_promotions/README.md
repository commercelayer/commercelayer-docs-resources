---
description: >-
  The external promotion object and the allowed CRUD operations on the related
  resource endpoint
---

# External promotions

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](https://docs.commercelayer.io/api/resources/promotions) and [promotion rules](https://docs.commercelayer.io/api/resources/promotion\_rules).

Besides the promotion types that are supported out-of-the-box Commerce Layer lets you integrate any kind of promotional engine as an external promotion. When triggered, external promotions are responsible for adding the externally computed discount to the orders invoved. When an external promotion activates, Commerce Layer triggers a POST request to the promotion URL endpoint, sending the order payload (including its line items) in the request body. The external service response (or error) must match the format described in [this example](https://docs.commercelayer.io/api/external-resources/external-promotions).

Within the time window given by their activation and expiration dates, external promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active external promotion, the computed discount is applied to all the orders in the specified currency (or to all the orders of the market in scope if the promotion is restricted to a specific market). Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them.

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/external-resources/external-promotions) for any additional info on how to configure your external promotion engine and integrate it with Commerce Layer.

</details>
