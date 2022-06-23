---
description: How to create a price via API
---

# Create a price

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new price, send a `POST` request to the `/api/prices` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/prices</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**sku_code** | `string` | Optional |
| attributes.**amount_cents** | `integer` | Required |
| attributes.**compare_at_amount_cents** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**price_list** | `object` | Required |
| relationships.**sku** | `object` | Optional |
| relationships.**price_tiers** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new price:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/prices' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "prices",
    "attributes": {
      "amount_cents": 10000,
      "compare_at_amount_cents": 13000
    },
    "relationships": {
      "price_list": {
        "data": {
          "type": "price_lists",
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
    "type": "prices",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde"
    },
    "attributes": {
      "currency_code": "EUR",
      "sku_code": "TSHIRTMM000000FFFFFFXLXX",
      "amount_cents": 10000,
      "amount_float": 100.0,
      "formatted_amount": "€100,00",
      "compare_at_amount_cents": 13000,
      "compare_at_amount_float": 130.0,
      "formatted_compare_at_amount": "€130,00",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "price_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/relationships/price_list",
          "related": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/price_list"
        }
      },
      "sku": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/relationships/sku",
          "related": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/sku"
        }
      },
      "price_tiers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/relationships/price_tiers",
          "related": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/price_tiers"
        }
      },
      "price_volume_tiers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/relationships/price_volume_tiers",
          "related": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/price_volume_tiers"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/prices/xYZkjABcde/attachments"
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

