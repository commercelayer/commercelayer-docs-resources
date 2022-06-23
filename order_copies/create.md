---
description: How to create an order copy via API
---

# Create an order copy

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new order copy, send a `POST` request to the `/api/order_copies` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/order_copies</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**place_target_order** | `boolean` | Optional |
| attributes.**cancel_source_order** | `boolean` | Optional |
| attributes.**reuse_wallet** | `boolean` | Optional, default is 'true' |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**source_order** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new order copy:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/order_copies' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "order_copies",
    "relationships": {
      "source_order": {
        "data": {
          "type": "orders",
          "id": "QWERtyUpBa"
        }
      }
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created resource object:

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
  }
}
```
{% endtab %}
{% endtabs %}

