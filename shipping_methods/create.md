---
description: How to create a shipping method via API
---

# Create a shipping method

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new shipping method, send a `POST` request to the `/api/shipping_methods` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/shipping_methods</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**scheme** | `string` | Optional, default to 'flat' |
| attributes.**currency_code** | `string` | Required, unless inherited by market |
| attributes.**price_amount_cents** | `integer` | Required |
| attributes.**free_over_amount_cents** | `integer` | Optional |
| attributes.**min_weight** | `float` | Optional |
| attributes.**max_weight** | `float` | Optional |
| attributes.**unit_of_weight** | `string` | Optional, unless min or max weight are specified |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**market** | `object` | Optional |
| relationships.**shipping_zone** | `object` | Optional |
| relationships.**shipping_category** | `object` | Optional |
| relationships.**stock_location** | `object` | Optional |
| relationships.**shipping_method_tiers** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new shipping method:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/shipping_methods' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "shipping_methods",
    "attributes": {
      "name": "Standard shipping",
      "currency_code": "EUR",
      "price_amount_cents": 1000
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
    "type": "shipping_methods",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde"
    },
    "attributes": {
      "name": "Standard shipping",
      "scheme": "flat",
      "currency_code": "EUR",
      "disabled_at": "2018-01-01T12:00:00.000Z",
      "price_amount_cents": 1000,
      "price_amount_float": 10.0,
      "formatted_price_amount": "???10,00",
      "free_over_amount_cents": 9900,
      "free_over_amount_float": 99.0,
      "formatted_free_over_amount": "???99,00",
      "price_amount_for_shipment_cents": 0,
      "price_amount_for_shipment_float": 0.0,
      "formatted_price_amount_for_shipment": "???0,00",
      "min_weight": 3.0,
      "max_weight": 300.0,
      "unit_of_weight": "gr",
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
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/market"
        }
      },
      "shipping_zone": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_zone",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_zone"
        }
      },
      "shipping_category": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_category",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_category"
        }
      },
      "stock_location": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/stock_location",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/stock_location"
        }
      },
      "delivery_lead_time_for_shipment": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/delivery_lead_time_for_shipment",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/delivery_lead_time_for_shipment"
        }
      },
      "shipping_method_tiers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_method_tiers",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_method_tiers"
        }
      },
      "shipping_weight_tiers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_weight_tiers",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_weight_tiers"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/attachments"
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

