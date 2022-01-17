---
description: How to create a klarna payment via API
---

# Create a klarna payment

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new klarna payment, send a `POST` request to the `/api/klarna_payments` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/klarna_payments</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**order** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new klarna payment:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/klarna_payments' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "klarna_payments",
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

