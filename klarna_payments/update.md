---
description: How to update an existing klarna payment via API
---

# Update a klarna payment

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing klarna payment, send a `PATCH` request to the `/api/klarna_payments/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/klarna_payments/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**auth_token** | `string` | Optional |
| attributes.**_update** | `boolean, value is 'true'` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**order** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the klarna payment identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "klarna_payments",
    "id": "xYZkjABcde",
    "attributes": {
      "reference": "ANY-EXTERNAL-REFEFERNCE"
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
      "formatted_intent_amount": "???10,00",
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

