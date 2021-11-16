---
description: How to create a taxjar account via API
---

# Create a taxjar account

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new taxjar account, send a `POST` request to the `/api/taxjar_accounts` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/taxjar_accounts</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| attributes.**api_key** | `string` | Required |
| relationships.**tax_categories** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new taxjar account:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/taxjar_accounts' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "taxjar_accounts",
    "attributes": {
      "name": "Personal tax calculator",
      "api_key": "TAXJAR_API_KEY"
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
    "type": "taxjar_accounts",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde"
    },
    "attributes": {
      "name": "Personal tax calculator",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "tax_categories": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/tax_categories",
          "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/tax_categories"
        }
      },
      "markets": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/markets",
          "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/markets"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/attachments"
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

