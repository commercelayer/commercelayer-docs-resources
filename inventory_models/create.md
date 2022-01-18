---
description: How to create an inventory model via API
---

# Create an inventory model

To [create](https://docs.commercelayer.io/developers/creating-resources) a new inventory model, send a `POST` request to the `/api/inventory_models` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/inventory\_models**

### Arguments

| Body Parameter                          | Type      | Required               |
| --------------------------------------- | --------- | ---------------------- |
| **type**                                | `string`  | Required               |
| attributes.**name**                     | `string`  | Required               |
| attributes.**strategy**                 | `string`  | Required               |
| attributes.**stock\_locations\_cutoff** | `integer` | Optional, default is 2 |
| attributes.**reference**                | `string`  | Optional               |
| attributes.**reference\_origin**        | `string`  | Optional               |
| attributes.**metadata**                 | `object`  | Optional               |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new inventory model:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/inventory_models' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "inventory_models",
    "attributes": {
      "name": "EU Inventory Model",
      "strategy": "split_shipments"
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
