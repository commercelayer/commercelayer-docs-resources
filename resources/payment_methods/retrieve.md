---
description: How to fetch a specific payment method via API
---

# Retrieve a payment method

To fetch a single payment method, send a `GET` request to the `/api/payment_methods/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/payment_methods/:id

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the payment method identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde' \
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
    "type": "payment_methods",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde"
    },
    "attributes": {
      "payment_source_type": "CreditCard",
      "name": "Credit Card",
      "disabled_at": "2018-01-01T12:00:00.000Z",
      "price_amount_cents": 0,
      "price_amount_float": 0.0,
      "formatted_price_amount": "€0,00",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/market"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/payment_gateway"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/attachments"
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

