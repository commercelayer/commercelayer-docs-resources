---
description: How to fetch a collection of parcel line items via API
---

# List all parcel line items

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of parcel line items, send a `GET` request to the `/api/parcel_line_items` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/parcel_line_items

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of parcel line items:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/parcel_line_items/' \
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
      "type": "parcel_line_items",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde"
      },
      "attributes": {
        "sku_code": "TSHIRTMM000000FFFFFFXLXX",
        "quantity": 4,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "parcel": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/relationships/parcel",
            "related": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/parcel"
          }
        },
        "stock_line_item": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/relationships/stock_line_item",
            "related": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/stock_line_item"
          }
        },
        "shipment_line_item": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/relationships/shipment_line_item",
            "related": "https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde/shipment_line_item"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 parcel_line_items (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/parcel_line_items?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/parcel_line_items?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/parcel_line_items?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of parcel line items can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `quantity`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

