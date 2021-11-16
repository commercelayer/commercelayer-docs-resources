---
description: How to fetch a collection of order subscriptions via API
---

# List all order subscriptions

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of order subscriptions, send a `GET` request to the `/api/order_subscriptions` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/order_subscriptions**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of order subscriptions:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_subscriptions/' \
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
    },
    {
      "other": "... 9 order_subscriptions (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/order_subscriptions?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/order_subscriptions?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/order_subscriptions?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of order subscriptions can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `number`
* `status`
* `frequency`
* `starts_at`
* `expires_at`
* `next_run_at`
* `errors_count`
* `succeeded_on_last_run`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

