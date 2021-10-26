---
description: How to update an existing attachment via API
---

# Update an attachment

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing attachment, send a `PATCH` request to the `/api/attachments/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://<i></i>yourdomain.commercelayer.io/api/attachments/:id

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**name** | `string` | Optional |
| attributes.**description** | `string` | Optional |
| attributes.**url** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**attachable** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the attachment identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "attachments",
    "id": "xYZkjABcde",
    "attributes": {
      "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
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
    "type": "attachments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde"
    },
    "attributes": {
      "name": "DDT transport document",
      "description": "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
      "url": "https://s3.yourdomain.com/attachment.pdf",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "attachable": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde/relationships/attachable",
          "related": "https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde/attachable"
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

