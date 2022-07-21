---
description: >-
  The stock location object and the allowed CRUD operations on the related
  resource endpoint
---

# Stock locations

Stock locations contain the inventory of the [SKUs](../skus/) that are being sold in terms of [stock items](../stock\_items/) and their quantity. The stock location's address is the "From" address on the shipping labels.

The list of [inventory stock locations](../inventory\_stock\_locations/) determines the availability of SKUs that are being purchased. The list of [inventory return locations](../inventory\_return\_locations/) determines the available options for returns.

Based on the selected inventory model strategy [stock transfers](../stock\_transfers/) might be created from a stock location (i.e. secondary) from another (i.e. primary).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/stock-locations) and explore the flowchart that illustrates how the stock location resource relates to the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/inventory-model-strategies) to learn more about the available inventory model strategies, how they work, and how stock locations are involved in the process.

</details>
