---
description: >-
  The coupon object and the allowed CRUD operations on the related resource
  endpoint
---

# Coupons

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

Coupons must be associated with [coupon code](../coupon\_codes\_promotion\_rules/) promotions rules so that a promotion is triggered when customers enter a specific coupon code at checkout. The coupon can be used multiple times and it is considered valid until its usage count exceeds the threshold set by its usage limit. About that:

* Set the `usage_limit` attribute to `1` if you want the code to be used just once.
* Set the `customer_single_use` attribute to `true` if you want it to be used just once per customer.
