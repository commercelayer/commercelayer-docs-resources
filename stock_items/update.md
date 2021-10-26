---
description: How to update an existing stock item via API
---

# Update a stock item

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing stock item, send a `PATCH` request to the `/api/stock_items/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://<i></i>yourdomain.commercelayer.io/api/stock_items/:id

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**sku_code** | `string` | Optional |
| attributes.**quantity** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**stock_location** | `object` | Optional |
| relationships.**sku** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the stock item identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/stock_items/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "stock_items",
    "id": "xYZkjABcde",
    "attributes": {
      "sku_code": "TSHIRTMM000000FFFFFFXLXX"
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning the updated resource object:

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

