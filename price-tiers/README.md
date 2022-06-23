---
description: >-
  The price tier object and the allowed CRUD operations on the related resource
  endpoint
---

# Price tiers

Price tiers let you segment the pricing of your products by defining specific intervals where the unit price of the associated SKU stays the same (changing when each interval's upper limit is exceeded).

At the moment [volume tiers](../price-volume-tiers/) are available for prices (more to come).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/price-lists-and-currencies) and explore the flowchart that illustrates how the price tier resource relates to the other API entities.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of price tiers or a specific single one.
{% endhint %}
