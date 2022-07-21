---
description: >-
  The stock transfer object and the allowed CRUD operations on the related
  resource endpoint
---

# Stock transfers

An order can be configured to ship from a specific [stock location](../stock\_locations/) only (e.g. primary). In this scenario, the number of shipments is minimized by creating one or more stock transfers from the stock location where the items are available to the primary one. [Shipping categories](../shipping\_categories/) are still honored, by creating different shipments.

Stock transfers can also be created outside of the order scope. In this case, they have no relationships with [shipments](../shipments/) and [line items](../line\_items/).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/stock-transfers) and explore the flowchart that illustrates how the stock transfer resource relates to the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) to learn more about the available inventory model strategies, how they work, and how stock transfers are managed based on each of them.

</details>
