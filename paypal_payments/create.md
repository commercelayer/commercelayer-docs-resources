---
description: How to create a paypal payment via API
---

# Create a paypal payment

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new paypal payment, send a `POST` request to the `/api/paypal_payments` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/paypal_payments</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**return_url** | `string` | Required |
| attributes.**cancel_url** | `string` | Required |
| attributes.**note_to_payer** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**order** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new paypal payment:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/paypal_payments' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "paypal_payments",
    "attributes": {
      "return_url": "https://yourdomain.com/thankyou",
      "cancel_url": "https://yourdomain.com/checkout/payment"
    },
    "relationships": {
      "order": {
        "data": {
          "type": "orders",
          "id": "QWERtyUpBa"
        }
      }
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "paypal_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde"
    },
    "attributes": {
      "return_url": "https://yourdomain.com/thankyou",
      "cancel_url": "https://yourdomain.com/checkout/payment",
      "note_to_payer": "Thank you for shopping with us!",
      "paypal_payer_id": "ABCDEFGHG123456",
      "name": "ABCDEFGHG123456",
      "paypal_id": "1234567890",
      "status": "created",
      "approval_url": "https://www.paypal.com/cgi-bin/webscr?cmd=_express-checkout&token=EC-1234567890ABCDEFGHG",
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
          "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/payment_gateway"
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

