---
description: >-
  The external gateway object and the allowed CRUD operations on the related
  resource endpoint
---

# External gateways

External payment gateways let you integrate any payment service that is not available out-of-the-box (even your custom one) and safely process any type of external payment.

To create an external gateway choose a meaningful name that helps you identify it within your organization and specify the endpoints you have configured externally. You need to provide your gateway's **authorize**, **capture**, **void**, **refund**, and **customer token** URLs. Your external endpoint will be responsible for the actual integration with the payment gateway. The payment source associated with the order must be an [external payment](../external\_payments/).

External gateways process payments **synchronously** by default. You can use the webhook endpoint URL Commerce Layer exposes to manage [async payments](https://docs.commercelayer.io/developers/external-resources/external-payment-gateways#asynchronous-payments).

<details>

<summary>How-to</summary>

Check the related [guide](https://docs.commercelayer.io/developers/external-resources/external-payment-gateways) for any additional info on how to configure your external payment gateway and integrate it with Commerce Layer.

</details>
