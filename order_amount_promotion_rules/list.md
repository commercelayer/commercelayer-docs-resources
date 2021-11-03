---
description: How to fetch a collection of order amount promotion rules via API
---

# List all order amount promotion rules

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of order amount promotion rules, send a `GET` request to the `/api/order_amount_promotion_rules` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/order_amount_promotion_rules

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of order amount promotion rules:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_amount_promotion_rules/' \
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
      "type": "order_amount_promotion_rules",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules/xYZkjABcde"
      },
      "attributes": {
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        },
        "order_amount_cents": 1000,
        "order_amount_float": 10.0,
        "formatted_order_amount": "€10,00"
      },
      "relationships": {
        "promotion": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules/xYZkjABcde/relationships/promotion",
            "related": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules/xYZkjABcde/promotion"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 order_amount_promotion_rules (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/order_amount_promotion_rules?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of order amount promotion rules can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
* `order_amount_cents`

