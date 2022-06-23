---
description: >-
  The price volume tier object and the allowed CRUD operations on the related
  resource endpoint
---

# Price volume tiers

Price volume tiers let you segment the pricing of your products by defining different prices for specific intervals based on volume. The price of the associated SKU will be set by the tier the total quantity of items purchased falls within. For each tier the main attributes you need to specify are:

* `up_to` — the tier's upper limit (in terms of the SKU's quantity).
* `price_amount_cents` — the unit price to be used for the related SKU if the total quantity of the associated line item is lower than (or equal to) the `up_to` limit.

If the `up_to` attribute is `null` the related tier will be considered a _beyond_ tier, meaning that the specified unit price will be used if the SKU's quantity is greater than the maximum tier's upper limit. If no _beyond_ tier is set the standard SKU's [price](../prices/object.md) `amount_cents` will be used as the _beyond_ price.

{% hint style="info" %}
A maximum of **5 tiers per price** are currently allowed.
{% endhint %}
