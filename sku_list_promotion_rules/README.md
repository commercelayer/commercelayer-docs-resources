---
description: >-
  The SKU list promotion rule object and the allowed CRUD operations on the
  related resource endpoint
---

# SKU list promotion rules

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

SKU list promotions rules are used to trigger the associated promotion only if an order contains any (default) or all (set the `all_skus` attribute to `true`) of the SKUs within the specified list. Optionally, is possible to specify a `min_quantity`, which will overwrite previous rules and will be honoured by checking the order's line items quantities and the matching SKU list item (this rule does **not** apply to [bundles](../bundles/)).
