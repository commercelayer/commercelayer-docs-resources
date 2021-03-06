---
description: >-
  The carrier account object and the allowed CRUD operations on the related
  resource endpoint
---

# Carrier accounts

Commerce Layer integrates with **100+ shipping carriers** via [Easypost](https://www.easypost.com/carriers).

You can set up a carrier account from the admin UI. All you need to do is select the carrier type and provide all the credentials requested by the selected shipping service.

Configuring a carrier account for a market is optional and enables you to purchase and print shipping labels in one click and provide real-time tracking updates to your customers. You can connect more carriers to the same market to get more rate options and choose the best one for each shipment.

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipping-carriers) and explore the flowchart that illustrates how the carrier account resource relates to the other API entities.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of carrier accounts or a specific single one.
{% endhint %}
