---
description: >-
  The bundle object and the allowed CRUD operations on the related resource
  endpoint
---

# Bundles

Bundles describe a set of specific products that are being sold. A unique code identifies each bundle. The bundle name, description, and image URL are best suited for internal usage (Commerce Layer is not a CMS). Bundles are linked to manual SKU lists, inheriting the SKUs from there.&#x20;

{% hint style="info" %}
A **maximum of 5 SKU list items** are permitted for each bundle. Once an SKU list is associated with a bundle, its items cannot be added, removed, or updated, unless you first destroy all of the linked bundles.
{% endhint %}

Bundles have `price_amount_cents` and `compare_at_amount_cents` attributes: the latter can be specified or computed as the sum of the SKUs, but is always guaranteed to be smaller or equal than the former. Once a price is assigned to a bundle, the currency is inherited by the relationship with the market. If that relationship is not specified, a currency must be assigned to the bundle.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/bundles) and explore the flowchart that illustrates how the bundle resource relates to the other API entities.

</details>
