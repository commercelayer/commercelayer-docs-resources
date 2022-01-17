---
description: >-
  The payment gateway object and the allowed CRUD operations on the related
  resource endpoint
---

# Payment gateways

Commerce Layer is integrated out-of-the-box with some of the most common payment gateways, all compliant with the [PSD2 European regulation](https://ec.europa.eu/info/law/payment-services-psd-2-directive-eu-2015-2366\_en) so that you can implement a payment flow that supports [SCA](https://en.wikipedia.org/wiki/Strong\_customer\_authentication) and [3DS2](https://3dsecure2.com) by using the specific gateway official JS SDK.

The currently supported gateways are:

* [Adyen](../adyen\_gateways/)
* [Braintree](../braintree\_gateways/)
* [Checkout.com](../checkout\_com\_gateways/)
* [PayPal](../paypal\_gateways/)
* [Stripe](../stripe\_gateways/)

Other types of gateways are also available, such as:

* [External gateways](../external\_gateways/) — to integrate any other payment service that is not available out-of-the-box (even your custom one).
* [Manual gateways](../manual\_gateways/) — useful to process wire transfers, cash payments, and other kinds of manual payments.

You can set up a payment gateway from the admin UI. All you need to do is select the type of gateway you want to use and provide all the credentials requested by the selected payment service.

Configuring a payment gateway for a market lets you safely process payments through the API. You can connect different gateways to different markets through the available [payment methods](../payment\_methods/).

<details>

<summary>Data model</summary>

Check the related [ER diagram](https://commercelayer.io/docs/data-model/payment-gateways) and explore the flowchart that illustrates how the payment gateway resource relates with the other API entities.

</details>

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/v/how-tos/payments) to learn more on how Commerce Layer handles the server-side part of the integration process with each specific gateway.

</details>

{% hint style="info" %}
This is an **immutable API**, meaning that create, update, and delete operations are not allowed on this endpoint. You can only fetch a list of payment gateways or a specific single one.
{% endhint %}
