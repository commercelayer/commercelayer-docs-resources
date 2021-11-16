---
description: How to update an existing inventory model via API
---

# Update an inventory model

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing inventory model, send a `PATCH` request to the `/api/inventory_models/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/inventory_models/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**name** | `string` | Optional |
| attributes.**strategy** | `string` | Optional |
| attributes.**stock_locations_cutoff** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the inventory model identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "inventory_models",
    "id": "xYZkjABcde",
    "attributes": {
      "reference": "ANY-EXTERNAL-REFEFERNCE"
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
    "type": "inventory_models",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde"
    },
    "attributes": {
      "name": "EU Inventory Model",
      "strategy": "split_shipments",
      "stock_locations_cutoff": 3,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "inventory_stock_locations": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/relationships/inventory_stock_locations",
          "related": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/inventory_stock_locations"
        }
      },
      "inventory_return_locations": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/relationships/inventory_return_locations",
          "related": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/inventory_return_locations"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/attachments"
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

