---
description: How to fetch a collection of shipping categories via API
---

# List all shipping categories

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of shipping categories, send a `GET` request to the `/api/shipping_categories` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/shipping_categories</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of shipping categories:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/shipping_categories/' \
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
      "type": "shipping_categories",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde"
      },
      "attributes": {
        "name": "Merchandise",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "skus": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/relationships/skus",
            "related": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/skus"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 shipping_categories (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/shipping_categories?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/shipping_categories?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/shipping_categories?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of shipping categories can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

