---
description: How to update an existing SKU via API
---

# Update a SKU

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing SKU, send a `PATCH` request to the `/api/skus/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/skus/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**code** | `string` | Optional |
| attributes.**name** | `string` | Optional |
| attributes.**description** | `string` | Optional |
| attributes.**image_url** | `string` | Optional |
| attributes.**pieces_per_pack** | `integer` | Optional |
| attributes.**weight** | `float` | Optional |
| attributes.**unit_of_weight** | `string` | Optional |
| attributes.**hs_tariff_number** | `string` | Optional |
| attributes.**do_not_ship** | `boolean` | Optional |
| attributes.**do_not_track** | `boolean` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**shipping_category** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the SKU identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/skus/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "skus",
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
    "type": "skus",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde"
    },
    "attributes": {
      "code": "TSHIRTMM000000FFFFFFXLXX",
      "name": "Black Men T-shirt with White Logo (XL)",
      "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
      "image_url": "https://img.yourdomain.com/skus/xYZkjABcde.png",
      "pieces_per_pack": 6,
      "weight": 300.0,
      "unit_of_weight": "gr",
      "hs_tariff_number": "4901.91.0020",
      "do_not_ship": false,
      "do_not_track": false,
      "inventory": {
        "available": true,
        "quantity": 10,
        "levels": [
          {
            "quantity": 4,
            "delivery_lead_times": [
              {
                "shipping_method": {
                  "name": "Standard Shipping",
                  "reference": null,
                  "price_amount_cents": 700,
                  "free_over_amount_cents": 9900,
                  "formatted_price_amount": "€7,00",
                  "formatted_free_over_amount": "€99,00"
                },
                "min": {
                  "hours": 72,
                  "days": 3
                },
                "max": {
                  "hours": 120,
                  "days": 5
                }
              },
              {
                "shipping_method": {
                  "name": "Express Delivery",
                  "reference": null,
                  "price_amount_cents": 1200,
                  "free_over_amount_cents": null,
                  "formatted_price_amount": "€12,00",
                  "formatted_free_over_amount": null
                },
                "min": {
                  "hours": 48,
                  "days": 2
                },
                "max": {
                  "hours": 72,
                  "days": 3
                }
              }
            ]
          },
          {
            "quantity": 6,
            "delivery_lead_times": [
              {
                "shipping_method": {
                  "name": "Standard Shipping",
                  "reference": null,
                  "price_amount_cents": 700,
                  "free_over_amount_cents": 9900,
                  "formatted_price_amount": "€7,00",
                  "formatted_free_over_amount": "€99,00"
                },
                "min": {
                  "hours": 96,
                  "days": 4
                },
                "max": {
                  "hours": 144,
                  "days": 6
                }
              },
              {
                "shipping_method": {
                  "name": "Express Delivery",
                  "reference": null,
                  "price_amount_cents": 1200,
                  "free_over_amount_cents": null,
                  "formatted_price_amount": "€12,00",
                  "formatted_free_over_amount": null
                },
                "min": {
                  "hours": 72,
                  "days": 3
                },
                "max": {
                  "hours": 96,
                  "days": 4
                }
              }
            ]
          }
        ]
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
      "shipping_category": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/shipping_category",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/shipping_category"
        }
      },
      "prices": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/prices",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/prices"
        }
      },
      "stock_items": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/stock_items",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/stock_items"
        }
      },
      "delivery_lead_times": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/delivery_lead_times",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/delivery_lead_times"
        }
      },
      "sku_options": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/sku_options",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/sku_options"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/attachments"
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

