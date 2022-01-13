---
description: >-
  The order copy object and the allowed CRUD operations on the related resource
  endpoint
---

# Order copies

Order copies generate asynchronously a copy of a source order and all of its associated line items, line item options, payment source (if stored within the customer wallet) and addresses.

They can be used standalone to allow orders editing (no matter their state) or generated recursively as part of an order subscription, in which case they are usually automatically placed according to a specified frequency.

You can set different options, based on how you want the order copy process to be performed:

* `place_target_order` — the copied order is going to be placed at the end of the process; default for order subscriptions.
* `cancel_source_order` — the source order is going to be cancelled at the end of the process.
