---
description: >-
  The inventory model object and the allowed CRUD operations on the related
  resource endpoint
---

# Inventory models

An inventory model defines a list of [stock locations](../stock\_locations/) ordered by priority. The priority and cutoff determine how the availability of SKUs gets calculated within a market.&#x20;

The list of [inventory stock locations](../inventory\_stock\_locations/) determines the availability of SKUs that are being purchased. The list of [inventory return locations](../inventory\_return\_locations/) determines the available options for returns.

### Inventory strategies

Multiple [inventory model strategies](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) are available. You can select a specific one by setting the `strategy` attribute accordingly, depending on how you want your order items to be fulfilled. An inventory model strategy is responsible to decide how many [shipments](../shipments/) are generated and from which stock location each shipment will be shipped. Based on the selected strategy, if an order contains line items from two or more stock locations, the order can be split into two or more shipments, one for each location. [Stock transfers](../stock\_transfers/) from a stock location (e.g. secondary) to another (e.g. primary) can be created as well.

{% hint style="info" %}
In case the inventory model strategy is left as default – **no split** – just a single shipment from a single stock location is always created.
{% endhint %}

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/inventory-models) and explore the flowchart that illustrates how the inventory model resource relates to the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) to learn more about the available inventory model strategies and how they work.

</details>
