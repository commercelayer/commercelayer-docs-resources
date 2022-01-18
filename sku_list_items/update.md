---
description: How to update an existing SKU list item via API
---

# Update a SKU list item

To [update](https://docs.commercelayer.io/developers/updating-resources) an existing SKU list item, send a `PATCH` request to the `/api/sku_list_items/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/sku\_list\_items/:id**

### Arguments

| Body Parameter                   | Type      | Required |
| -------------------------------- | --------- | -------- |
| **type**                         | `string`  | Required |
| **id**                           | `string`  | Required |
| attributes.**position**          | `integer` | Optional |
| attributes.**sku\_code**         | `string`  | Optional |
| attributes.**quantity**          | `integer` | Optional |
| attributes.**reference**         | `string`  | Optional |
| attributes.**reference\_origin** | `string`  | Optional |
| attributes.**metadata**          | `object`  | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the SKU list item identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "sku_list_items",
    "id": "xYZkjABcde",
    "attributes": {
      "position": 2
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
