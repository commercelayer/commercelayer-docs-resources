---
description: How to fetch a specific order copy via API
---

# Retrieve an order copy

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single order copy, send a `GET` request to the `/api/order_copies/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/order_copies/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the order copy identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde' \
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
  }
}
```
{% endtab %}
{% endtabs %}

