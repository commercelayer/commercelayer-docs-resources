---
description: How to fetch a specific fixed price promotion via API
---

# Retrieve a fixed price promotion

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single fixed price promotion, send a `GET` request to the `/api/fixed_price_promotions/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/fixed_price_promotions/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the fixed price promotion identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "fixed_price_promotions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde"
    },
    "attributes": {
      "name": "Personal promotion",
      "currency_code": "EUR",
      "starts_at": "2018-01-01T12:00:00.000Z",
      "expires_at": "2018-01-02T12:00:00.000Z",
      "total_usage_limit": 5,
      "total_usage_count": 2,
      "active": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "fixed_amount_cents": 1000,
      "fixed_amount_float": 10.0,
      "formatted_fixed_amount": "€10,00"
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/market"
        }
      },
      "promotion_rules": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/promotion_rules",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/promotion_rules"
        }
      },
      "order_amount_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/order_amount_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/order_amount_promotion_rule"
        }
      },
      "sku_list_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/sku_list_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/sku_list_promotion_rule"
        }
      },
      "coupon_codes_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/coupon_codes_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/coupon_codes_promotion_rule"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/attachments"
        }
      },
      "sku_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/sku_list",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/sku_list"
        }
      },
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde/skus"
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

