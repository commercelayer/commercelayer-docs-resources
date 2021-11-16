---
description: How to fetch a specific SKU list promotion rule via API
---

# Retrieve a SKU list promotion rule

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single SKU list promotion rule, send a `GET` request to the `/api/sku_list_promotion_rules/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/sku_list_promotion_rules/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the SKU list promotion rule identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde' \
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
    "type": "sku_list_promotion_rules",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde"
    },
    "attributes": {
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "all_skus": true,
      "min_quantity": 3
    },
    "relationships": {
      "promotion": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/relationships/promotion",
          "related": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/promotion"
        }
      },
      "sku_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/relationships/sku_list",
          "related": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/sku_list"
        }
      },
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/sku_list_promotion_rules/xYZkjABcde/skus"
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

