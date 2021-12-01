---
description: How to create a SKU list item via API
---

# Create a SKU list item

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new SKU list item, send a `POST` request to the `/api/sku_list_items` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/sku_list_items</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**position** | `integer` | Optional |
| attributes.**sku_code** | `string` | Optional |
| attributes.**quantity** | `integer` | Optional, default to '1' |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**sku_list** | `object` | Required |
| relationships.**sku** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new SKU list item:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/sku_list_items' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "sku_list_items",
    "relationships": {
      "sku_list": {
        "data": {
          "type": "sku_lists",
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
    "type": "sku_list_items",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde"
    },
    "attributes": {
      "position": 2,
      "sku_code": "TSHIRTMM000000FFFFFFXLXX",
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
  }
}
```
{% endtab %}
{% endtabs %}

