---
description: How to fetch a specific event callback via API
---

# Retrieve an event callback

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single event callback, send a `GET` request to the `/api/event_callbacks/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/event\_callbacks/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the event callback identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/event_callbacks/xYZkjABcde' \
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
    "type": "event_callbacks",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/event_callbacks/xYZkjABcde"
    },
    "attributes": {
      "callback_url": "https://yourapp.com/webhooks",
      "payload": {
        "data": {
          "attributes": {
            "id": "PYWehaoXJj",
            "type": "orders"
          }
        }
      },
      "response_code": "200",
      "response_message": "OK",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "webhook": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/event_callbacks/xYZkjABcde/relationships/webhook",
          "related": "https://yourdomain.commercelayer.io/api/event_callbacks/xYZkjABcde/webhook"
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
