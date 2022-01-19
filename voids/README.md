---
description: >-
  The void object and the allowed CRUD operations on the related resource
  endpoint
---

# Voids

Before being approved an [order](../orders/) can be cancelled. On successful cancellation, the order's payment status becomes `voided` and a new void transaction is created.

Fetching a void returns all the information and messages provided by the [payment gateway](../payment\_gateways/).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/orders-management) and explore the flowchart that illustrates how the void resource relates to the order and the transaction APIs.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of voids or a specific single one.
{% endhint %}
