---
description: How to create a stock item via API
---

# Create a stock item

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new stock item, send a `POST` request to the `/api/stock_items` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/stock_items**

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**sku_code** | `string` | Optional |
| attributes.**quantity** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**stock_location** | `object` | Required |
| relationships.**sku** | `object` | Required, if not set through the sku_code attribute |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new stock item:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/stock_items' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "stock_items",
    "attributes": {
      "quantity": 100
    },
    "relationships": {
      "stock_location": {
        "data": {
          "type": "stock_locations",
          "id": "QWERtyUpBa"
        }
      },
      "sku": {
        "data": {
          "type": "skus",
          "id": "QWERtyUpBa"
        }
      }
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "stock_items",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde"
    },
    "attributes": {
      "sku_code": "TSHIRTMM000000FFFFFFXLXX",
      "quantity": 100,
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
          "self": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/relationships/stock_location",
          "related": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/stock_location"
        }
      },
      "sku": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/relationships/sku",
          "related": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/sku"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde/attachments"
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

