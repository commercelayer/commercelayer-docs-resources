---
description: How to create a customer via API
---

# Create a customer

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new customer, send a `POST` request to the `/api/customers` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://<i></i>yourdomain.commercelayer.io/api/customers

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**email** | `string` | Required |
| attributes.**password** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**customer_group** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new customer:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/customers' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "customers",
    "attributes": {
      "email": "john@example.com"
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
  }
}
```
{% endtab %}
{% endtabs %}

