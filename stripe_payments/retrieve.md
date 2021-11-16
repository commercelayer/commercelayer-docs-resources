---
description: How to fetch a specific stripe payment via API
---

# Retrieve a stripe payment

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single stripe payment, send a `GET` request to the `/api/stripe_payments/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/stripe_payments/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the stripe payment identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde' \
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
    "type": "stripe_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde"
    },
    "attributes": {
      "client_secret": "pi_1234XXX_secret_5678YYY",
      "publishable_key": "pk_live_xxxx-yyyy-zzzz",
      "options": {
        "customer": "cus_xxx",
        "payment_method": "pm_xxx"
      },
      "payment_method": {
        "id": "pm_xxx"
      },
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "order": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/payment_gateway"
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

