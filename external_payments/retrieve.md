---
description: How to fetch a specific external payment via API
---

# Retrieve an external payment

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single external payment, send a `GET` request to the `/api/external_payments/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/external_payments/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the external payment identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde' \
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
    "type": "external_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde"
    },
    "attributes": {
      "payment_source_token": "xxxx.yyyy.zzzz",
      "options": {
        "foo": "bar"
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
          "self": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/payment_gateway"
        }
      },
      "wallet": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/relationships/wallet",
          "related": "https://yourdomain.commercelayer.io/api/external_payments/xYZkjABcde/wallet"
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

