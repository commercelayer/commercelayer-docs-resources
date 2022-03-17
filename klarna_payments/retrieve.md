---
description: How to fetch a specific klarna payment via API
---

# Retrieve a klarna payment

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single klarna payment, send a `GET` request to the `/api/klarna_payments/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/klarna_payments/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the klarna payment identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde' \
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
    "type": "klarna_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde"
    },
    "attributes": {
      "session_id": "xxxx-yyyy-zzzz",
      "client_token": "xxxx-yyyy-zzzz",
      "payment_methods": [
        {
          "foo": "bar"
        }
      ],
      "auth_token": "xxxx-yyyy-zzzz",
      "mismatched_amounts": false,
      "intent_amount_cents": 1000,
      "intent_amount_float": 10.0,
      "formatted_intent_amount": "€10,00",
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
          "self": "https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde/payment_gateway"
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

