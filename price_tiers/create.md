---
description: How to create a price tier via API
---

# Create a price tier

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new price tier, send a `POST` request to the `/api/price_tiers` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/price_tiers</b>

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
| relationships.**price** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new price tier:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/price_tiers' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "price_tiers",
    "attributes": {
      "name": "six pack",
      "price_amount_cents": 1000
    },
    "relationships": {
      "price": {
        "data": {
          "type": "prices",
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
    "type": "price_tiers",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde"
    },
    "attributes": {
      "name": "six pack",
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
      "price": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/relationships/price",
          "related": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/price"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/attachments"
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

