---
description: >-
  The shipping category object and the allowed CRUD operations on the related
  resource endpoint
---

# Shipping categories

Shipping categories determine which [shipping methods](../shipping\_methods/) are available for the associated [SKUs](../skus/). Unless the selected inventory model strategy is [no split](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies/no-split), if an order contains line items belonging to more than one shipping category it is split into more [shipments](../shipments/).

{% hint style="info" %}
In case the inventory model strategy is left as default – **no split** – just a single shipment is always created, no matter if the order contains SKUs associated with different shipping categories. In this case, the number of available shipping methods will increase accordingly since they won't be filtered by shipping category.
{% endhint %}

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipments-and-shipping-categories) and explore the flowchart that illustrates how the shipping category resource relates to the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) to learn more about the available inventory model strategies, how they work, and how shipping categories are involved in the process.

</details>
