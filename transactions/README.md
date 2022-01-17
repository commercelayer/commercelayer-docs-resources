---
description: >-
  The transaction object and the allowed CRUD operations on the related resource
  endpoint
---

# Transactions

Transactions are created during an order lifecycle and determine its payment status changes:

* [Authorizations](../authorizations/) — when a payment source is authorized. On successful authorization the order's payment status becomes `authorized`.&#x20;
* [Captures](../captures/) — when an authorization is captured. On successful capture the order's payment status becomes `paid`.&#x20;
* [Voids](../voids/) — when an authorization is voided. On successful void the order's payment status becomes `voided`.
* [Refunds](../refunds/) — when a capture is refunded, either totally or partially. On successful refund the order's payment status becomes `refunded` or `partially_refunded`.

Fetching a transaction returns all the information and messages provided by the [payment gateway](../payment\_gateways/).

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of transactions or a specific single one.
{% endhint %}
