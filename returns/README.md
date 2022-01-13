---
description: >-
  The return object and the allowed CRUD operations on the related resource
  endpoint
---

# Returns

Returns are linked to one specific order. They get created in "draft" status and become "pending" when a customer requests to return SKUs from an order. Pending returns can be "approved" or "rejected". An approved return becomes "shipped" once it leaves the customer address. Returns are marked "received" once they reach the available return location, where they can be restocked to an inventory location.
