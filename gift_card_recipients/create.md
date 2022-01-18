---
description: How to create a gift card recipient via API
---

# Create a gift card recipient

To [create](https://docs.commercelayer.io/developers/creating-resources) a new gift card recipient, send a `POST` request to the `/api/gift_card_recipients` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/gift\_card\_recipients**

### Arguments

| Body Parameter                   | Type     | Required |
| -------------------------------- | -------- | -------- |
| **type**                         | `string` | Required |
| attributes.**email**             | `string` | Required |
| attributes.**first\_name**       | `string` | Optional |
| attributes.**last\_name**        | `string` | Optional |
| attributes.**reference**         | `string` | Optional |
| attributes.**reference\_origin** | `string` | Optional |
| attributes.**metadata**          | `object` | Optional |
| relationships.**customer**       | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new gift card recipient:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/gift_card_recipients' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "gift_card_recipients",
    "attributes": {
      "email": "john@example.com"
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
    "type": "gift_card_recipients",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde"
    },
    "attributes": {
      "email": "john@example.com",
      "first_name": "John",
      "last_name": "Smith",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "customer": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde/relationships/customer",
          "related": "https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde/customer"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde/attachments"
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
