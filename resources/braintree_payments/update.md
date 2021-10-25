---
description: How to update an existing braintree payment via API
---

# Update a braintree payment

To update an existing braintree payment, send a `PATCH` request to the `/api/braintree_payments/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

{% page-ref page="../../updating-resources.md" %}

## Request

**PATCH** https://<i></i>yourdomain.commercelayer.io/api/braintree_payments/:id

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**payment_method_nonce** | `string` | Optional |
| attributes.**payment_id** | `string` | Optional |
| attributes.**local** | `boolean` | Optional |
| attributes.**options** | `object` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**order** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the braintree payment identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "braintree_payments",
    "id": "xYZkjABcde",
    "attributes": {
      "payment_method_nonce": "xxxx.yyyy.zzzz"
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning the updated resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "braintree_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde"
    },
    "attributes": {
      "client_token": "xxxx.yyyy.zzzz",
      "payment_method_nonce": "xxxx.yyyy.zzzz",
      "payment_id": "xxxx.yyyy.zzzz",
      "local": true,
      "options": {
        "customer_id": "1234567890"
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
          "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/payment_gateway"
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

