---
description: How to create a market via API
---

# Create a market

To [create](https://docs.commercelayer.io/developers/creating-resources) a new market, send a `POST` request to the `/api/markets` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/markets**

### Arguments

| Body Parameter                       | Type     | Required |
| ------------------------------------ | -------- | -------- |
| **type**                             | `string` | Required |
| attributes.**name**                  | `string` | Required |
| attributes.**facebook\_pixel\_id**   | `string` | Optional |
| attributes.**checkout\_url**         | `string` | Optional |
| attributes.**external\_prices\_url** | `string` | Optional |
| attributes.**reference**             | `string` | Optional |
| attributes.**reference\_origin**     | `string` | Optional |
| attributes.**metadata**              | `object` | Optional |
| relationships.**merchant**           | `object` | Required |
| relationships.**price\_list**        | `object` | Required |
| relationships.**inventory\_model**   | `object` | Required |
| relationships.**tax\_calculator**    | `object` | Optional |
| relationships.**customer\_group**    | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new market:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/markets' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "markets",
    "attributes": {
      "name": "EU Market"
    },
    "relationships": {
      "merchant": {
        "data": {
          "type": "merchants",
          "id": "QWERtyUpBa"
        }
      },
      "price_list": {
        "data": {
          "type": "price_lists",
          "id": "QWERtyUpBa"
        }
      },
      "inventory_model": {
        "data": {
          "type": "inventory_models",
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
    "type": "markets",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde"
    },
    "attributes": {
      "number": 1234,
      "name": "EU Market",
      "facebook_pixel_id": "1234567890",
      "checkout_url": "https://checkout.yourbrand.com/:order_id",
      "external_prices_url": "https://external_prices.yourbrand.com",
      "private": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "merchant": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/merchant",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/merchant"
        }
      },
      "price_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/price_list",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/price_list"
        }
      },
      "inventory_model": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/inventory_model",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/inventory_model"
        }
      },
      "tax_calculator": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/tax_calculator",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/tax_calculator"
        }
      },
      "customer_group": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/customer_group",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/customer_group"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/markets/xYZkjABcde/attachments"
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
