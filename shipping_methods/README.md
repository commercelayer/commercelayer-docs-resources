---
description: >-
  The shipping method object and the allowed CRUD operations on the related
  resource endpoint
---

# Shipping methods

Shipping methods are used to provide customers with different delivery options.&#x20;

Shipping methods are defined by currency and can be restricted to a [market](../markets/) (in the latter case the currency is inherited by the market's price list).&#x20;

* Set the `shipping_category` relationship if you want the shipping method to be available only if the items to be shipped belong to a specified [shipping category](../shipping\_categories/).
* Set the `shipping_zone` relationship if you want the shipping method to be available only if the shipping address belongs to a specified [shipping zone](../shipping\_zones/).
* Set the `stock_location` relationship if you want the shipping method to be available only if the items are shipped from a specific stock location.
* Specify a value for the `min_weight` and/or `max_weight` attributes (to do that also a `unit_of_weight` must be defined) if you want the shipping method to be available only if the total weight of the items to be shipped falls within those values.

{% hint style="info" %}
The total weight of the shipment is automatically calculated from the single weights of the items included (i.e. the `weight` attribute of the [SKUs](../skus/object.md) to be shipped).
{% endhint %}

Each shipping method can have a price and can be free over a specific order's amount. Set the proper value for the `scheme` attribute (default is `flat`) to define how you want to manage the shipping method cost:

* `flat` — the shipping method has a fixed price (equal to the value of the `price_amount_cents` attribute).
* `weight_tiered` — the shipping method price is [tiered](../shipping-method-tiers/) based on the total weight of the items included in the shipment (a maximum of **5** tiers for each shipping method is currently supported). See [shipping weight tiers](../shipping-weight-tiers/) to learn more.

{% hint style="info" %}
If a `free_over_amount` was specified, it applies regardless of the tier. If a `min_weight` and/or `max_weight` value for the shipping method's availability was specified, only the tiers between those values will be considered.
{% endhint %}

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/checkout/selecting-a-shipping-method) to learn how to let a user choose one of the available shipping methods during the checkout.

</details>

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/shipping-zones-and-methods) and explore the flowchart that illustrates how the shipping method resource relates to the other API entities.

</details>
