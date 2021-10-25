---
description: How to fetch a specific stripe gateway via API
---

# Retrieve a stripe gateway

To fetch a single stripe gateway, send a `GET` request to the `/api/stripe_gateways/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/stripe_gateways/:id

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the stripe gateway identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "stripe_gateways",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde"
    },
    "attributes": {
      "name": "US payment gateway",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "webhook_endpoint_id": "xxxx-yyyy-zzzz",
      "webhook_endpoint_secret": "xxxx-yyyy-zzzz",
      "webhook_endpoint_url": "https://core.commercelayer.co/webhook_callbacks/stripe_gateways/xxxxx"
    },
    "relationships": {
      "payment_methods": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde/relationships/payment_methods",
          "related": "https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde/payment_methods"
        }
      },
      "stripe_payments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde/relationships/stripe_payments",
          "related": "https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde/stripe_payments"
        }
      }
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

