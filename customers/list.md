---
description: How to fetch a collection of customers via API
---

# List all customers

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of customers, send a `GET` request to the `/api/customers` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/customers</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of customers:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customers/' \
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
      "type": "customers",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde"
      },
      "attributes": {
        "email": "john@example.com",
        "status": "prospect",
        "has_password": false,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "customer_group": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/customer_group",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/customer_group"
          }
        },
        "customer_addresses": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/customer_addresses",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/customer_addresses"
          }
        },
        "customer_payment_sources": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/customer_payment_sources",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/customer_payment_sources"
          }
        },
        "customer_subscriptions": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/customer_subscriptions",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/customer_subscriptions"
          }
        },
        "orders": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/orders",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/orders"
          }
        },
        "order_subscriptions": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/order_subscriptions",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/order_subscriptions"
          }
        },
        "returns": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/returns",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/returns"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/customers/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 customers (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/customers?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/customers?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/customers?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of customers can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

