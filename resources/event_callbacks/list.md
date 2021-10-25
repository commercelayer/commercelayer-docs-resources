---
description: How to fetch a collection of event callbacks via API
---

# List all event callbacks

To fetch a collection of event callbacks, send a `GET` request to the `/api/event_callbacks` endpoint.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/event_callbacks

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of event callbacks:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/event_callbacks/' \
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
    },
    {
      "other": "... 9 event_callbacks (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/event_callbacks?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/event_callbacks?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/event_callbacks?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of event callbacks can be sorted by the following attributes:

* `response_code`
* `response_message`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

