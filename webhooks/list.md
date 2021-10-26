---
description: How to fetch a collection of webhooks via API
---

# List all webhooks

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of webhooks, send a `GET` request to the `/api/webhooks` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/webhooks

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of webhooks:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/webhooks/' \
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
      "type": "webhooks",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde"
      },
      "attributes": {
        "name": "myorg-orders.place",
        "topic": "orders.place",
        "callback_url": "https://yourapp.com/webhooks",
        "include_resources": [
          "customer",
          "shipping_address",
          "billing_address"
        ],
        "circuit_state": "closed",
        "circuit_failure_count": 5,
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
            "self": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde/relationships/last_event_callbacks",
            "related": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde/last_event_callbacks"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 webhooks (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/webhooks?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/webhooks?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/webhooks?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of webhooks can be sorted by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

