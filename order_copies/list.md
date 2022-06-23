---
description: How to fetch a collection of order copies via API
---

# List all order copies

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of order copies, send a `GET` request to the `/api/order_copies` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/order_copies</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of order copies:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_copies/' \
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
      "type": "order_copies",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde"
      },
      "attributes": {
        "status": "in_progress",
        "started_at": "2018-01-01T12:00:00.000Z",
        "completed_at": "2018-01-01T12:00:00.000Z",
        "failed_at": "2018-01-01T12:00:00.000Z",
        "place_target_order": true,
        "cancel_source_order": true,
        "reuse_wallet": true,
        "errors_log": {
          "status": [
            "cannot transition from draft to placed"
          ]
        },
        "errors_count": 2,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "source_order": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/relationships/source_order",
            "related": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/source_order"
          }
        },
        "target_order": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/relationships/target_order",
            "related": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/target_order"
          }
        },
        "order_subscription": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/relationships/order_subscription",
            "related": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/order_subscription"
          }
        },
        "events": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/relationships/events",
            "related": "https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde/events"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 order_copies (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/order_copies?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/order_copies?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/order_copies?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of order copies can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `status`
* `started_at`
* `completed_at`
* `failed_at`
* `errors_count`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

