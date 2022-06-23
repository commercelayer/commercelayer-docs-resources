---
description: How to fetch a collection of events via API
---

# List all events

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of events, send a `GET` request to the `/api/events` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/events</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of events:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/events/' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a paginated collection of resource objects:

```javascript
{
  "data": [
    {
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
    },
    {
      "other": "... 9 events (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/events?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/events?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/events?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of events can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

