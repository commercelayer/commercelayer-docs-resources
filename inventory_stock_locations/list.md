---
description: How to fetch a collection of inventory stock locations via API
---

# List all inventory stock locations

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of inventory stock locations, send a `GET` request to the `/api/inventory_stock_locations` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/inventory_stock_locations

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of inventory stock locations:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/inventory_stock_locations/' \
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
      "type": "inventory_stock_locations",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde"
      },
      "attributes": {
        "priority": 1,
        "on_hold": false,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "stock_location": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde/relationships/stock_location",
            "related": "https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde/stock_location"
          }
        },
        "inventory_model": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde/relationships/inventory_model",
            "related": "https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde/inventory_model"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 inventory_stock_locations (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/inventory_stock_locations?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/inventory_stock_locations?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/inventory_stock_locations?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of inventory stock locations can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `priority`
* `on_hold`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

