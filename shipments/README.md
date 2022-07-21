---
description: >-
  The shipment object and the allowed CRUD operations on the related resource
  endpoint
---

# Shipments

The default inventory model strategy is [no split](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies/no-split), meaning that just a single shipment from a single stock location is always created. If a different strategy is selected the orders fulfillment can be split into more shipments for one of the following reasons:

* The order contains line items from more than one [stock location](../stock\_locations/).
* The order contains line items belonging to more than one [shipping category](../shipping\_categories/).

The combination of stock locations and shipping categories determines the number of shipments. Each shipment gets fulfilled separately.

{% hint style="info" %}
In case the inventory model strategy is left as default – **no split** – shipping categories are ignored: just one shipment is created with no specific category associated.
{% endhint %}

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipments-and-shipping-categories) and explore the flowchart that illustrates how the shipment resource relates to the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) to learn more about the available inventory model strategies, how they work, and how shipments are managed based on each of them.

</details>
