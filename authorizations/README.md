---
description: >-
  The authorization object and the allowed CRUD operations on the related
  resource endpoint
---

# Authorizations

When an [order](../orders/) is placed a successful authorization transaction is created and the order's payment status becomes `authorized` (except for async payments, i.e. [Stripe](../stripe\_payments/))

Fetching an authorization returns all the information and messages provided by the [payment gateway](../payment\_gateways/). You can update an authorization to [capture](../captures/) or [void](../voids/) it.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/orders-management) and explore the flowchart that illustrates how the authorization resource relates to the order and the other transaction APIs.

</details>
