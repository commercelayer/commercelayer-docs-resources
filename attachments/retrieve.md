---
description: How to fetch a specific attachment via API
---

# Retrieve an attachment

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single attachment, send a `GET` request to the `/api/attachments/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/attachments/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the attachment identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

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

