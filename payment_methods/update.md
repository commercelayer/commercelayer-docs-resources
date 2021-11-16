---
description: How to update an existing payment method via API
---

# Update a payment method

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing payment method, send a `PATCH` request to the `/api/payment_methods/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/payment_methods/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**payment_source_type** | `string` | Optional |
| attributes.**price_amount_cents** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**market** | `object` | Optional |
| relationships.**payment_gateway** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the payment method identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "payment_methods",
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

