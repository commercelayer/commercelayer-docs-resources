---
description: >-
  The parcel line item object and the allowed CRUD operations on the related
  resource endpoint
---

# Parcel line items

Parcel line items track the SKUs in the related [parcel](../parcels/).&#x20;

* If a stock line item in a shipment is not split, the parcel line items correspond to the stock line item's SKUs.
* If a stock line item is split, the line items are split into more than one parcel line item. A single stock line item can also be split into more than one parcel line item.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/parcels-and-packages) and explore the flowchart that illustrates how the parcel line item resource relates with the other API entities.

</details>
