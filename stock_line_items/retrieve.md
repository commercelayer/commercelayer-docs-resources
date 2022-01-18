---
description: How to fetch a specific stock line item via API
---

# Retrieve a stock line item

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single stock line item, send a `GET` request to the `/api/stock_line_items/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/stock\_line\_items/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the stock line item identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde' \
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
    "type": "stock_line_items",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde"
    },
    "attributes": {
      "sku_code": "TSHIRTMM000000FFFFFFXLXX",
      "bundle_code": "BUNDLEMM000000FFFFFFXLXX",
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
      "shipment": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/relationships/shipment",
          "related": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/shipment"
        }
      },
      "line_item": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/relationships/line_item",
          "related": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/line_item"
        }
      },
      "stock_item": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/relationships/stock_item",
          "related": "https://yourdomain.commercelayer.io/api/stock_line_items/xYZkjABcde/stock_item"
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
