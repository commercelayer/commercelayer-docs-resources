---
description: How to create an avalara account via API
---

# Create an avalara account

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new avalara account, send a `POST` request to the `/api/avalara_accounts` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/avalara_accounts</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| attributes.**username** | `string` | Required |
| attributes.**password** | `string` | Required |
| attributes.**company_code** | `string` | Required |
| attributes.**ddp** | `string` | Optional |
| relationships.**tax_categories** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new avalara account:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/avalara_accounts' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "avalara_accounts",
    "attributes": {
      "name": "Personal tax calculator",
      "username": "user@mydomain.com",
      "password": "secret",
      "company_code": "MYCOMPANY"
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
    "type": "avalara_accounts",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde"
    },
    "attributes": {
      "name": "Personal tax calculator",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "username": "user@mydomain.com",
      "company_code": "MYCOMPANY",
      "ddp": "true"
    },
    "relationships": {
      "tax_categories": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/relationships/tax_categories",
          "related": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/tax_categories"
        }
      },
      "markets": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/relationships/markets",
          "related": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/markets"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde/attachments"
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

