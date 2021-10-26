---
description: How to fetch a specific order subscription via API
---

# Retrieve an order subscription

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single order subscription, send a `GET` request to the `/api/order_subscriptions/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/order_subscriptions/:id

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the order subscription identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde' \
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

