---
description: How to create a billing info validation rule via API
---

# Create a billing info validation rule

To [create](https://docs.commercelayer.io/developers/creating-resources) a new billing info validation rule, send a `POST` request to the `/api/billing_info_validation_rules` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/billing\_info\_validation\_rules**

### Arguments

| Body Parameter                   | Type     | Required |
| -------------------------------- | -------- | -------- |
| **type**                         | `string` | Required |
| attributes.**reference**         | `string` | Optional |
| attributes.**reference\_origin** | `string` | Optional |
| attributes.**metadata**          | `object` | Optional |
| relationships.**market**         | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new billing info validation rule:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/billing_info_validation_rules' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "billing_info_validation_rules",
    "relationships": {
      "market": {
        "data": {
          "type": "markets",
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
    "type": "billing_info_validation_rules",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde"
    },
    "attributes": {
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde/market"
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
