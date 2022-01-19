---
description: >-
  The refund object and the allowed CRUD operations on the related resource
  endpoint
---

# Refunds

A [captured](../captures/) payment can be refunded, either totally or partially. The total refund amount cannot exceed the amount captured — if it’s equal to the amount captured the refund will be full, if it’s less the refund will be partial**:**

* In case of a **partial refund**, the related order's payment status is moved to `partially_refunded` and a new successful refund transaction is created.
* In case of a **full refund**, the order status is moved to `cancelled`, its payment status to `refunded`, and a new successful refund transaction is created.

Fetching a refund returns all the information and messages provided by the [payment gateway](../payment\_gateways/).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/orders-management) and explore the flowchart that illustrates how the refund resource relates to the order and the other transaction APIs.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of refunds or a specific single one.
{% endhint %}
