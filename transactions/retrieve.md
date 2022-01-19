---
description: How to fetch a specific transaction via API
---

# Retrieve a transaction

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single transaction, send a `GET` request to the `/api/transactions/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/transactions/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the transaction identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/transactions/xYZkjABcde' \
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
    "type": "transactions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/transactions/xYZkjABcde"
    },
    "attributes": {
      "number": "42/T/001",
      "currency_code": "EUR",
      "amount_cents": 1500,
      "amount_float": 15.0,
      "formatted_amount": "€15,00",
      "succeeded": false,
      "message": "Accepted",
      "error_code": "00001",
      "error_detail": "Already settled",
      "token": "xxxx-yyyy-zzzz",
      "gateway_transaction_id": "xxxx-yyyy-zzzz",
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
          "self": "https://yourdomain.commercelayer.io/api/transactions/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/transactions/xYZkjABcde/order"
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

