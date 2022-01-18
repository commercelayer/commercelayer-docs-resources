---
description: How to fetch a collection of return line items via API
---

# List all return line items

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of return line items, send a `GET` request to the `/api/return_line_items` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/return\_line\_items**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of return line items:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/return_line_items/' \
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
      "type": "return_line_items",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/return_line_items/xYZkjABcde"
      },
      "attributes": {
        "sku_code": "TSHIRTMM000000FFFFFFXLXX",
        "bundle_code": "BUNDLEMM000000FFFFFFXLXX",
        "name": "Black Men T-shirt with White Logo (XL)",
        "quantity": 4,
        "return_reason": {
          "size": "was wrong"
        },
        "restocked_at": "2018-01-01T12:00:00.000Z",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "return": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/return_line_items/xYZkjABcde/relationships/return",
            "related": "https://yourdomain.commercelayer.io/api/return_line_items/xYZkjABcde/return"
          }
        },
        "line_item": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/return_line_items/xYZkjABcde/relationships/line_item",
            "related": "https://yourdomain.commercelayer.io/api/return_line_items/xYZkjABcde/line_item"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 return_line_items (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/return_line_items?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/return_line_items?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/return_line_items?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of return line items can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `quantity`
* `restocked_at`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
