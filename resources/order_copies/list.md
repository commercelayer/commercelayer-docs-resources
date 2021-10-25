---
description: How to fetch a collection of order copies via API
---

# List all order copies

To fetch a collection of order copies, send a `GET` request to the `/api/order_copies` endpoint.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/order_copies

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

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of order copies can be sorted by the following attributes:

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

{% page-ref page="../../sorting-results.md" %}

