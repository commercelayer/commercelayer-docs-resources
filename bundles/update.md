---
description: How to update an existing bundle via API
---

# Update a bundle

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing bundle, send a `PATCH` request to the `/api/bundles/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/bundles/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**code** | `string` | Optional |
| attributes.**name** | `string` | Optional |
| attributes.**currency_code** | `string` | Optional |
| attributes.**description** | `string` | Optional |
| attributes.**image_url** | `string` | Optional |
| attributes.**price_amount_cents** | `integer` | Optional |
| attributes.**compare_at_amount_cents** | `integer` | Optional |
| attributes.**_compute_price_amount** | `boolean, value is 'true'` | Optional |
| attributes.**_compute_compare_at_amount** | `boolean, value is 'true'` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the bundle identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "bundles",
    "id": "xYZkjABcde",
    "attributes": {
      "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
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
    "type": "bundles",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde"
    },
    "attributes": {
      "code": "BUNDMM000000FFFFFFXLXX",
      "name": "Black Men T-shirt (XL) with Black Cap and Socks, all with White Logo",
      "currency_code": "EUR",
      "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
      "image_url": "https://img.yourdomain.com/bundles/xYZkjABcde.png",
      "price_amount_cents": 10000,
      "price_amount_float": 100.0,
      "formatted_price_amount": "€100,00",
      "compare_at_amount_cents": 13000,
      "compare_at_amount_float": 130.0,
      "formatted_compare_at_amount": "€130,00",
      "skus_count": 2,
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
          "self": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/market"
        }
      },
      "sku_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/relationships/sku_list",
          "related": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/sku_list"
        }
      },
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/skus"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/bundles/xYZkjABcde/attachments"
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

