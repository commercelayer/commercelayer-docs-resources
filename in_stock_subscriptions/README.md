---
description: >-
  The in-stock subscription object and the allowed CRUD operations on the
  related resource endpoint
---

# In-stock subscriptions

An "in-stock" subscription tracks the customer interest for an SKU that has gone out of stock in a given market. When the SKU returns back in stock, all the active subscriptions receive a 'notify' event and you can attach a webhook to actually notify the customer via email or any other channel. It's possible to set a `stock_threshold` as the minimum value to identify an SKU as back in stock (default is `1`).
