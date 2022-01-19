---
description: How to update an existing gift card recipient via API
---

# Update a gift card recipient

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing gift card recipient, send a `PATCH` request to the `/api/gift_card_recipients/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/gift_card_recipients/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**email** | `string` | Optional |
| attributes.**first_name** | `string` | Optional |
| attributes.**last_name** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**customer** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the gift card recipient identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "gift_card_recipients",
    "id": "xYZkjABcde",
    "attributes": {
      "first_name": "John"
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

