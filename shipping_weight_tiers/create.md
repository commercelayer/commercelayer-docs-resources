---
description: How to create a shipping weight tier via API
---

# Create a shipping weight tier

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new shipping weight tier, send a `POST` request to the `/api/shipping_weight_tiers` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/shipping_weight_tiers</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**up_to** | `float` | Optional |
| attributes.**price_amount_cents** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**shipping_method** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new shipping weight tier:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/shipping_weight_tiers' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "shipping_weight_tiers",
    "attributes": {
      "name": "Light shipping under 3kg",
      "price_amount_cents": 1000
    },
    "relationships": {
      "shipping_method": {
        "data": {
          "type": "shipping_methods",
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
    "type": "shipping_weight_tiers",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde"
    },
    "attributes": {
      "name": "Light shipping under 3kg",
      "up_to": 20.5,
      "price_amount_cents": 1000,
      "price_amount_float": 10.0,
      "formatted_price_amount": "€10,00",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "shipping_method": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/relationships/shipping_method",
          "related": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/shipping_method"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/attachments"
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

