---
description: How to update an existing shipping method via API
---

# Update a shipping method

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing shipping method, send a `PATCH` request to the `/api/shipping_methods/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/shipping_methods/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**name** | `string` | Optional |
| attributes.**scheme** | `string` | Optional |
| attributes.**currency_code** | `string` | Optional |
| attributes.**_disable** | `boolean` | Optional |
| attributes.**_enable** | `boolean` | Optional |
| attributes.**price_amount_cents** | `integer` | Optional |
| attributes.**free_over_amount_cents** | `integer` | Optional |
| attributes.**min_weight** | `float` | Optional |
| attributes.**max_weight** | `float` | Optional |
| attributes.**unit_of_weight** | `string` | Optional |
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
The following request updates the shipping method identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "shipping_methods",
    "id": "xYZkjABcde",
    "attributes": {
      "_disable": true
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
      "formatted_price_amount": "€10,00",
      "free_over_amount_cents": 9900,
      "free_over_amount_float": 99.0,
      "formatted_free_over_amount": "€99,00",
      "price_amount_for_shipment_cents": 0,
      "price_amount_for_shipment_float": 0.0,
      "formatted_price_amount_for_shipment": "€0,00",
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

