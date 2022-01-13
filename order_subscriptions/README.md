---
description: >-
  The order subscription object and the allowed CRUD operations on the related
  resource endpoint
---

# Order subscriptions

Order subscriptions allow repeating a given source order according to a specified frequency: smaller is `daily`, larger is `yearly`.

Order subscriptions by default activates from a `placed` source order, which is considered the subscription's first run. In such case the subscription is marked as `active` and the next run will be scheduled on current timestamp.

In case you want full control over the order subscription, you can specify the `activate_by_source_order` option as `false` at creation time. In this case you are not limited to placed source orders (source order status isn't checked), but must define manually the `starts_at` time (`expires_at` time is optional). Also remember to use the `_activate` attribute to activate the subscription, otherwise it will miss the next run.

To suspend or cancel an order subscription you can use the `_deactivate` and `_cancel` attributes.

Order subscriptions rely on order copies to create periodic orders. A tentative to place the copied order is done at the end of the process. You can set the `place_target_order` option as `false` at creation time if you prefer to place created orders manually.

Currently, order subscriptions have no retry policy: in case, for any reason, the order copy fails, the `errors_count` counter is incremented, but the subscription is kept `active` (unless `expired`, `deactivated` or `cancelled`).

It is possible to check the `succeeded_on_last_run` attribute to inspect subscription last run state: in case its value is `false`, you can inspect the last associated `order_copy` to fix any missing/bad data and manually place the copied order.

You can attach `webhooks` on order subscriptions and order copies events, to act promptly in case something unexpected happens.
