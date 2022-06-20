---
description: >-
  The order object and the allowed CRUD operations on the related resource
  endpoint
---

# Orders

Orders get created in _draft_ status and become _pending_ when they have a customer and some line items.&#x20;

{% hint style="info" %}
Draft orders act as **shopping carts** — see our [how-to](https://docs.commercelayer.io/developers/v/how-tos/shopping-cart) on how to manage shopping carts.&#x20;
{% endhint %}

_Pending_ orders can be recovered when abandoned. The status of an order is strictly dependent on the related payment and fulfillment statuses. When an order is _placed_, it can either get _approved_ or _cancelled_. An approved order becomes _fulfilled_ when paid and shipped. Cancelling an order automatically [voids](../voids/) its payment source's [authorization](../authorizations/). Captured payments can be [refunded](../refunds/), either fully or partially.&#x20;

| Action                    | Order status | Payment status       | Fulfillment status                                     |
| ------------------------- | ------------ | -------------------- | ------------------------------------------------------ |
| **Order placement**       | `placed`     | `authorized`         | `unfulfilled`                                          |
| **Order cancellation**    | `cancelled`  | `voided`             | `unfulfilled`                                          |
| **Order approval**        | `approved`   | `authorized`         | `unfulfilled`                                          |
| **Payment capture**       | `approved`   | `paid`               | `in_progress`                                          |
| **Refund (partial)**      | `approved`   | `partially_refunded` | No changes to the previous fulfillment status.         |
| **Refund (full)**         | `cancelled`  | `refunded`           | `unfulfilled` if _in progress_, otherwise `fulfilled`. |
| **All shipments shipped** | `approved`   | `paid`               | `fulfilled`                                            |

<details>

<summary>Data model</summary>

Read more about the anatomy of an order [here](https://commercelayer.io/docs/data-model/anatomy-of-an-order) and check the related ER diagram that illustrates how the order resource relates to the other API entities.

</details>

### Idempotency

{% hint style="info" %}
Order status changes are **idempotent**. The order and payment statuses are granted to be consistent upon multiple updates (e.g. it's possible to place or cancel an order multiple times, without worrying about duplicated transactions and other side effects).
{% endhint %}

This can be useful to force a payment status (e.g. _paid_), in case the [payment gateway](../payment\_gateways/) has recorded the capture, but for some reason (typically the gateway's timeout) the order kept an inconsistent payment status (e.g. _authorized_). [Webhooks](../webhooks/)'s events, [stock item](../stock\_items/) updates, and other status-related actions are granted to be executed only once.
