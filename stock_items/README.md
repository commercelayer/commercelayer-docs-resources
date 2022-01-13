---
description: >-
  The stock item object and the allowed CRUD operations on the related resource
  endpoint
---

# Stock items

A stock item keeps the available inventory of an SKU in a given stock location. When you create a line item, the associated SKU must be available in one of the market's stock locations. When you place an order, the stock item quantities get decremented. When an order is canceled, or a return is approved, the stock item quantities get incremented.
