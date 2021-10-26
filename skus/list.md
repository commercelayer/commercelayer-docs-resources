---
description: How to fetch a collection of SKUs via API
---

# List all SKUs

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of SKUs, send a `GET` request to the `/api/skus` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/skus

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of SKUs:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/skus/' \
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
      "type": "skus",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde"
      },
      "attributes": {
        "code": "TSHIRTMM000000FFFFFFXLXX",
        "name": "Black Men T-shirt with White Logo (XL)",
        "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        "image_url": "https://img.yourdomain.com/skus/xYZkjABcde.png",
        "pieces_per_pack": 6,
        "weight": 300.0,
        "unit_of_weight": "gr",
        "hs_tariff_number": "4901.91.0020",
        "do_not_ship": false,
        "do_not_track": false,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "shipping_category": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/shipping_category",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/shipping_category"
          }
        },
        "prices": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/prices",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/prices"
          }
        },
        "stock_items": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/stock_items",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/stock_items"
          }
        },
        "delivery_lead_times": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/delivery_lead_times",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/delivery_lead_times"
          }
        },
        "sku_options": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/sku_options",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/sku_options"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/skus/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 skus (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/skus?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/skus?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/skus?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of SKUs can be sorted by the following attributes:

* `code`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

