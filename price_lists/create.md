---
description: How to create a price list via API
---

# Create a price list

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new price list, send a `POST` request to the `/api/price_lists` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/price_lists**

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**currency_code** | `string` | Required |
| attributes.**tax_included** | `boolean` | Optional, default is 'true' |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new price list:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/price_lists' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "price_lists",
    "attributes": {
      "name": "EU Price list",
      "currency_code": "EUR"
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
    "type": "price_lists",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde"
    },
    "attributes": {
      "name": "EU Price list",
      "currency_code": "EUR",
      "tax_included": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "prices": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/prices",
          "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/prices"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/attachments"
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

