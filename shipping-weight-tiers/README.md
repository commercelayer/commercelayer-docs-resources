---
description: >-
  The shipping weight tier object and the allowed CRUD operations on the related
  resource endpoint
---

# Shipping weight tiers



Shipping weight tiers let you segment the pricing of your shipping methods by defining different shipping method costs for specific intervals based on the weight of the associated shipment. The total weight of the shipment is automatically calculated from the single weights of the items included (i.e. the `weight` attribute of the [SKUs](../skus/object.md) to be shipped). For each tier the main attributes you need to specify are:

* `up_to` — the tier's upper limit (in terms of weight, the `unit_of_weight` will be inherited from the shipping method).
* `price_amount_cents` — the cost that will be charged for the shipping method if the total weight of the shipment is lower than (or equal to) the `up_to` limit.

If the `up_to` attribute is `null` the related tier will be considered a _beyond_ tier, meaning that the specified shipping method cost will be charged for all the shipments whose total weight is greater than the maximum tier's upper limit. If no _beyond_ tier is set the [shipping method](../shipping\_methods/object.md)'s `price_mount_cents` will be used as the _beyond_ price.

{% hint style="info" %}
A maximum of **5 weight tiers per shipping method** are currently allowed.
{% endhint %}
