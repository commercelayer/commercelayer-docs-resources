---
description: How to fetch a collection of SKU list items via API
---

# List all SKU list items

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of SKU list items, send a `GET` request to the `/api/sku_list_items` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/sku_list_items**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of SKU list items:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/sku_list_items/' \
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
      "type": "sku_list_items",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde"
      },
      "attributes": {
        "position": 2,
        "quantity": 1,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "sku_list": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde/relationships/sku_list",
            "related": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde/sku_list"
          }
        },
        "sku": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde/relationships/sku",
            "related": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde/sku"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 sku_list_items (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/sku_list_items?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/sku_list_items?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/sku_list_items?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of SKU list items can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `position`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

