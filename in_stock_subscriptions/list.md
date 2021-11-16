---
description: How to fetch a collection of in stock subscriptions via API
---

# List all in stock subscriptions

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of in stock subscriptions, send a `GET` request to the `/api/in_stock_subscriptions` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/in_stock_subscriptions</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of in stock subscriptions:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/in_stock_subscriptions/' \
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
      "type": "in_stock_subscriptions",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde"
      },
      "attributes": {
        "status": "active",
        "customer_email": "john@example.com",
        "sku_code": "TSHIRTMM000000FFFFFFXLXX",
        "stock_threshold": 3,
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
            "self": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/relationships/market",
            "related": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/market"
          }
        },
        "customer": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/relationships/customer",
            "related": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/customer"
          }
        },
        "sku": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/relationships/sku",
            "related": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde/sku"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 in_stock_subscriptions (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/in_stock_subscriptions?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of in stock subscriptions can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `status`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

