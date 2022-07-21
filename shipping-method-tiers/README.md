---
description: >-
  The shipping method tier object and the allowed CRUD operations on the related
  resource endpoint
---

# Shipping method tiers

Shipping method tiers let you segment the pricing of your [shipping methods](../shipping\_methods/) by defining specific intervals where the cost of the selected shipping method stays the same (changing when each interval's upper limit is exceeded).

At the moment [weight tiers](../shipping-weight-tiers/) are available for shipping methods (more to come).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipping-zones-and-methods) and explore the flowchart that illustrates how the shipping method tier resource relates to the other API entities.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of shipping method tiers or a specific single one.
{% endhint %}
