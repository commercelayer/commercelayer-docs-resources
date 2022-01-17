---
description: >-
  The stock line item object and the allowed CRUD operations on the related
  resource endpoint
---

# Stock line items

Stock line items track the SKUs in an order's shipment.

* If an order is not split, the stock line items correspond to all the SKUs in the order.
* If the order is split, the line items are split into more than one shipment. A single line item can also be split into more than one stock line item.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipments-and-shipping-categories) and explore the flowchart that illustrates how the stock line item resource relates with the other API entities.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of stock line items or a specific single one.
{% endhint %}
