---
description: How to fetch a specific merchant via API
---

# Retrieve a merchant

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single merchant, send a `GET` request to the `/api/merchants/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/merchants/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the merchant identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde' \
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
    "type": "merchants",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde"
    },
    "attributes": {
      "name": "The Brand Inc.",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "address": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/relationships/address",
          "related": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/address"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/attachments"
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

