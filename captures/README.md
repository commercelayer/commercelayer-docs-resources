---
description: >-
  The capture object and the allowed CRUD operations on the related resource
  endpoint
---

# Captures

When an [order](../orders/) is approved the associated payment can be captured. On successful capture, the order's payment status becomes `paid` and a new capture transaction is created.

Fetching a capture returns all the information and messages provided by the [payment gateway](../payment\_gateways/). You can update a capture to [refund](../refunds/) it.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/orders-management) and explore the flowchart that illustrates how the capture resource relates to the order and the other transaction APIs.

</details>
