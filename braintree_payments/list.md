---
description: How to fetch a collection of braintree payments via API
---

# List all braintree payments

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of braintree payments, send a `GET` request to the `/api/braintree_payments` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/braintree_payments**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of braintree payments:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/braintree_payments/' \
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
      "type": "braintree_payments",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde"
      },
      "attributes": {
        "client_token": "xxxx.yyyy.zzzz",
        "payment_method_nonce": "xxxx.yyyy.zzzz",
        "payment_id": "xxxx.yyyy.zzzz",
        "local": true,
        "options": {
          "customer_id": "1234567890"
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
        "order": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/relationships/order",
            "related": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/order"
          }
        },
        "payment_gateway": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/relationships/payment_gateway",
            "related": "https://yourdomain.commercelayer.io/api/braintree_payments/xYZkjABcde/payment_gateway"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 braintree_payments (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/braintree_payments?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/braintree_payments?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/braintree_payments?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of braintree payments can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

