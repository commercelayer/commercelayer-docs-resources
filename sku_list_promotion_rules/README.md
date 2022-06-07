---
description: >-
  The SKU list promotion rule object and the allowed CRUD operations on the
  related resource endpoint
---

# SKU list promotion rules

Commerce Layer provides a promotional engine built on top of two main resources: [promotions](../promotions/) and [promotion rules](../promotion\_rules/).

SKU list promotions rules are used to trigger the associated promotion only if an order contains any (default) or all (set the `all_skus` attribute to `true`) of the SKUs within the specified list. Optionally, is possible to specify a `min_quantity`, which will overwrite previous rules and will be honored by checking the order's line item quantities and the matching SKU list item.

{% hint style="info" %}
In order for an SKU list promotion rule to apply to [bundles](../bundles/), the two resources must share the same [SKU list](../sku\_lists/) (there is no SKUs partial matching). The `min_quantity` option will be checked against the quantity of the line item associated with the specific bundle.
{% endhint %}
