---
description: How to fetch a specific wire transfer via API
---

# Retrieve a wire transfer

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single wire transfer, send a `GET` request to the `/api/wire_transfers/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/wire_transfers/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the wire transfer identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/wire_transfers/xYZkjABcde' \
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
    "type": "wire_transfers",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/wire_transfers/xYZkjABcde"
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
      "order": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/wire_transfers/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/wire_transfers/xYZkjABcde/order"
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

