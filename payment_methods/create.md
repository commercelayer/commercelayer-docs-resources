---
description: How to create a payment method via API
---

# Create a payment method

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new payment method, send a `POST` request to the `/api/payment_methods` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/payment_methods</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**payment_source_type** | `string` | Required |
| attributes.**moto** | `boolean` | Optional, default is 'false' |
| attributes.**price_amount_cents** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**market** | `object` | Required |
| relationships.**payment_gateway** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new payment method:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/payment_methods' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "payment_methods",
    "attributes": {
      "payment_source_type": "CreditCard",
      "price_amount_cents": 0
    },
    "relationships": {
      "market": {
        "data": {
          "type": "markets",
          "id": "QWERtyUpBa"
        }
      },
      "payment_gateway": {
        "data": {
          "type": "payment_gateways",
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
    "type": "payment_methods",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde"
    },
    "attributes": {
      "payment_source_type": "CreditCard",
      "name": "Credit Card",
      "moto": false,
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

