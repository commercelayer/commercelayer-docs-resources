---
description: >-
  The SKU object and the allowed CRUD operations on the related resource
  endpoint
---

# SKUs

SKUs describe specific product variations that are being sold. A unique code identifies each SKU, which can be either the EAN code, the UPC, or any other code format. The SKU name, description, and image URL are best suited for internal usage (Commerce Layer is not a CMS). By marking an SKU with the `do_not_ship` and `do_not_track` combinable flags, is possible to manage different scenarios, such as intangible products which generate no shipments, or products with a virtually infinite stock.
