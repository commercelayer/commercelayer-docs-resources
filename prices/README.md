---
description: >-
  The price object and the allowed CRUD operations on the related resource
  endpoint
---

# Prices

[SKUs](../skus/) can have a price for each [price list](../price\_lists/). When you create a [line item](../line\_items/), it gets the price associated with the order's price list.&#x20;

{% hint style="info" %}
Some currencies have a zero exponent and cannot be expressed **in cents** (e.g. `JPY` and `HUF`). In such cases, you have to express the value as it is (e.g. `10000` JPY, not `1000000` JPY).
{% endhint %}

Prices can be [tiered](../price-tiers/) based on the quantity of the item purchased (a maximum of **5** tiers for each price is currently supported) — see [price volume tiers](../price-volume-tiers/) to learn more.

If you prefer not to manage prices within Commerce Layer but use an external service instead (e.g. to support more dynamic pricing or just rely on an existing service that you are already using) you can leverage our [external prices](https://docs.commercelayer.io/developers/external-resources/external-prices) feature.

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/external-resources/external-prices) to learn how to fetch and manage prices via external services.

</details>

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/price-lists-and-currencies) and explore the flowchart that illustrates how the price resource relates to the other API entities.

</details>
