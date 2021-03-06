---
description: How to fetch a collection of paypal payments via API
---

# List all paypal payments

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of paypal payments, send a `GET` request to the `/api/paypal_payments` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/paypal_payments</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of paypal payments:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/paypal_payments/' \
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
      "type": "paypal_payments",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde"
      },
      "attributes": {
        "return_url": "https://yourdomain.com/thankyou",
        "cancel_url": "https://yourdomain.com/checkout/payment",
        "note_to_payer": "Thank you for shopping with us!",
        "paypal_payer_id": "ABCDEFGHG123456",
        "name": "ABCDEFGHG123456",
        "paypal_id": "1234567890",
        "status": "created",
        "approval_url": "https://www.paypal.com/cgi-bin/webscr?cmd=_express-checkout&token=EC-1234567890ABCDEFGHG",
        "mismatched_amounts": false,
        "intent_amount_cents": 1000,
        "intent_amount_float": 10.0,
        "formatted_intent_amount": "€10,00",
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
            "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/relationships/order",
            "related": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/order"
          }
        },
        "payment_gateway": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/relationships/payment_gateway",
            "related": "https://yourdomain.commercelayer.io/api/paypal_payments/xYZkjABcde/payment_gateway"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 paypal_payments (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/paypal_payments?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/paypal_payments?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/paypal_payments?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of paypal payments can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

