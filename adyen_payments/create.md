---
description: How to create an adyen payment via API
---

# Create an adyen payment

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new adyen payment, send a `POST` request to the `/api/adyen_payments` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://<i></i>yourdomain.commercelayer.io/api/adyen_payments

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
The following request creates a new adyen payment:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/adyen_payments' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "adyen_payments",
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
    "type": "adyen_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde"
    },
    "attributes": {
      "public_key": "xxxx-yyyy-zzzz",
      "payment_methods": {
        "foo": "bar"
      },
      "payment_request_data": {
        "foo": "bar"
      },
      "payment_request_details": {
        "foo": "bar"
      },
      "payment_response": {
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
          "self": "https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde/payment_gateway"
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

