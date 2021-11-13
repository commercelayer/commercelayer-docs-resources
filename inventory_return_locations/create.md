---
description: How to create an inventory return location via API
---

# Create an inventory return location

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new inventory return location, send a `POST` request to the `/api/inventory_return_locations` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://<i></i>yourdomain.commercelayer.io/api/inventory_return_locations

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**priority** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**stock_location** | `object` | Required |
| relationships.**inventory_model** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new inventory return location:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/inventory_return_locations' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "inventory_return_locations",
    "attributes": {
      "priority": 1
    },
    "relationships": {
      "stock_location": {
        "data": {
          "type": "stock_locations",
          "id": "QWERtyUpBa"
        }
      },
      "inventory_model": {
        "data": {
          "type": "inventory_models",
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
    "type": "inventory_return_locations",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde"
    },
    "attributes": {
      "priority": 1,
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
          "self": "https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde/relationships/stock_location",
          "related": "https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde/stock_location"
        }
      },
      "inventory_model": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde/relationships/inventory_model",
          "related": "https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde/inventory_model"
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

