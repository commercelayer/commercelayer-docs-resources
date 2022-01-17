---
description: >-
  The package object and the allowed CRUD operations on the related resource
  endpoint
---

# Packages

Packages are physical packs or boxes stored in a stock location with specific sizes and ready for shipment. A package can contain two or more [parcels](../parcels/). Each stock location in a market can have its own set of defined packages with a pre-defined package `length`, `weight`, and `height`. That information about the package dimensions — required for the package creation — is used by [shipping carriers](../carrier\_accounts/) to calculate shipping rates.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/parcels-and-packages) and explore the flowchart that illustrates how the package resource relates with the other API entities.

</details>
