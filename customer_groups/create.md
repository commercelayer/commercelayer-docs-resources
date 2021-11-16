---
description: How to create a customer group via API
---

# Create a customer group

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new customer group, send a `POST` request to the `/api/customer_groups` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/customer_groups**

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new customer group:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/customer_groups' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "customer_groups",
    "attributes": {
      "name": "VIP"
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
    "type": "customer_groups",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde"
    },
    "attributes": {
      "name": "VIP",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "customers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/customers",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/customers"
        }
      },
      "markets": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/markets",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/markets"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/attachments"
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

