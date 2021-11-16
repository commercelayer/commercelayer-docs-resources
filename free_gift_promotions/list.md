---
description: How to fetch a collection of free gift promotions via API
---

# List all free gift promotions

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of free gift promotions, send a `GET` request to the `/api/free_gift_promotions` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/free_gift_promotions**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of free gift promotions:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/free_gift_promotions/' \
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
      "type": "free_gift_promotions",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde"
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
    },
    {
      "other": "... 9 free_gift_promotions (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/free_gift_promotions?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/free_gift_promotions?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/free_gift_promotions?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of free gift promotions can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `starts_at`
* `expires_at`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
* `max_quantity`

