---
description: How to fetch a collection of fixed price promotions via API
---

# List all fixed price promotions

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of fixed price promotions, send a `GET` request to the `/api/fixed_price_promotions` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/fixed_price_promotions

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of fixed price promotions:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/fixed_price_promotions/' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a paginated collection of resource objects:

```javascript
{
  "data": [
    {
      "id": "xYZkjABcde",
      "type": "fixed_price_promotions",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde"
      },
      "attributes": {
        "name": "Personal promotion",
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
    },
    {
      "other": "... 9 fixed_price_promotions (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/fixed_price_promotions?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/fixed_price_promotions?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/fixed_price_promotions?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of fixed price promotions can be sorted by the following attributes:

* `name`
* `starts_at`
* `expires_at`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
* `fixed_amount_cents`

{% page-ref page="../../sorting-results.md" %}

