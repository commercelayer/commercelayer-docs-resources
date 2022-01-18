---
description: How to fetch a specific free gift promotion via API
---

# Retrieve a free gift promotion

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single free gift promotion, send a `GET` request to the `/api/free_gift_promotions/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/free\_gift\_promotions/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the free gift promotion identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde' \
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
    "type": "free_gift_promotions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde"
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
      "max_quantity": 3
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/market"
        }
      },
      "promotion_rules": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/promotion_rules",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/promotion_rules"
        }
      },
      "order_amount_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/order_amount_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/order_amount_promotion_rule"
        }
      },
      "sku_list_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/sku_list_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/sku_list_promotion_rule"
        }
      },
      "coupon_codes_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/coupon_codes_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/coupon_codes_promotion_rule"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/attachments"
        }
      },
      "sku_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/sku_list",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/sku_list"
        }
      },
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde/skus"
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
