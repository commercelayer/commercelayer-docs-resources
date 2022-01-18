---
description: How to create a package via API
---

# Create a package

To [create](https://docs.commercelayer.io/developers/creating-resources) a new package, send a `POST` request to the `/api/packages` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/packages**

### Arguments

| Body Parameter                    | Type     | Required |
| --------------------------------- | -------- | -------- |
| **type**                          | `string` | Required |
| attributes.**name**               | `string` | Required |
| attributes.**code**               | `string` | Optional |
| attributes.**length**             | `float`  | Required |
| attributes.**width**              | `float`  | Required |
| attributes.**height**             | `float`  | Required |
| attributes.**unit\_of\_length**   | `string` | Required |
| attributes.**reference**          | `string` | Optional |
| attributes.**reference\_origin**  | `string` | Optional |
| attributes.**metadata**           | `object` | Optional |
| relationships.**stock\_location** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new package:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/packages' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "packages",
    "attributes": {
      "name": "Large (60x40x30)",
      "length": 40.0,
      "width": 40.0,
      "height": 25.0,
      "unit_of_length": "gr"
    },
    "relationships": {
      "stock_location": {
        "data": {
          "type": "stock_locations",
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
    "type": "packages",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde"
    },
    "attributes": {
      "name": "Large (60x40x30)",
      "code": "YYYY 2000",
      "length": 40.0,
      "width": 40.0,
      "height": 25.0,
      "unit_of_length": "gr",
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
          "self": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/relationships/stock_location",
          "related": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/stock_location"
        }
      },
      "parcels": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/relationships/parcels",
          "related": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/parcels"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/packages/xYZkjABcde/attachments"
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
