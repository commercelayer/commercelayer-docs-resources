---
description: How to create an order subscription via API
---

# Create an order subscription

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new order subscription, send a `POST` request to the `/api/order_subscriptions` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/order_subscriptions</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**frequency** | `string` | Required |
| attributes.**activate_by_source_order** | `boolean` | Optional |
| attributes.**starts_at** | `datetime` | Required, unless activate_by_source_order |
| attributes.**expires_at** | `datetime` | Optional |
| attributes.**options** | `object` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**market** | `object` | Optional |
| relationships.**source_order** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new order subscription:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/order_subscriptions' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "order_subscriptions",
    "attributes": {
      "frequency": "monthly",
      "starts_at": "2018-01-01T12:00:00.000Z"
    },
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
    "type": "order_subscriptions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde"
    },
    "attributes": {
      "number": "1234",
      "status": "draft",
      "frequency": "monthly",
      "activate_by_source_order": true,
      "customer_email": "john@example.com",
      "starts_at": "2018-01-01T12:00:00.000Z",
      "expires_at": "2018-01-02T12:00:00.000Z",
      "next_run_at": "2018-01-01T12:00:00.000Z",
      "occurrencies": 2,
      "errors_count": 3,
      "succeeded_on_last_run": true,
      "options": {
        "place_target_order": false
      },
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/market"
        }
      },
      "source_order": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/source_order",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/source_order"
        }
      },
      "customer": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/customer",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/customer"
        }
      },
      "order_copies": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/order_copies",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/order_copies"
        }
      },
      "orders": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/orders",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/orders"
        }
      },
      "events": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/relationships/events",
          "related": "https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde/events"
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

