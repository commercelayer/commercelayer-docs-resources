---
description: How to fetch a collection of captures via API
---

# List all captures

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of captures, send a `GET` request to the `/api/captures` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/captures</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of captures:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/captures/' \
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
      "type": "captures",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde"
      },
      "attributes": {
        "number": "42/T/001",
        "currency_code": "EUR",
        "amount_cents": 1500,
        "amount_float": 15.0,
        "formatted_amount": "€15,00",
        "succeeded": false,
        "message": "Accepted",
        "error_code": "00001",
        "error_detail": "Already settled",
        "token": "xxxx-yyyy-zzzz",
        "gateway_transaction_id": "xxxx-yyyy-zzzz",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        },
        "refund_amount_cents": 500,
        "refund_amount_float": 5.0,
        "formatted_refund_amount": "€5,00",
        "refund_balance_cents": 1000,
        "refund_balance_float": 10.0,
        "formatted_refund_balance": "€10,00"
      },
      "relationships": {
        "order": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/relationships/order",
            "related": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/order"
          }
        },
        "reference_authorization": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/relationships/reference_authorization",
            "related": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/reference_authorization"
          }
        },
        "refunds": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/relationships/refunds",
            "related": "https://yourdomain.commercelayer.io/api/captures/xYZkjABcde/refunds"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 captures (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/captures?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/captures?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/captures?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of captures can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `number`
* `amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

