---
description: How to fetch a specific event via API
---

# Retrieve an event

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single event, send a `GET` request to the `/api/events/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/events/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the event identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/events/xYZkjABcde' \
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
    "type": "events",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/events/xYZkjABcde"
    },
    "attributes": {
      "name": "orders.create",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "last_event_callbacks": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/events/xYZkjABcde/relationships/last_event_callbacks",
          "related": "https://yourdomain.commercelayer.io/api/events/xYZkjABcde/last_event_callbacks"
        }
      },
      "webhooks": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/events/xYZkjABcde/relationships/webhooks",
          "related": "https://yourdomain.commercelayer.io/api/events/xYZkjABcde/webhooks"
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

