---
description: How to create a checkout.com payment via API
---

# Create a checkout.com payment

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new checkout.com payment, send a `POST` request to the `/api/checkout_com_payments` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/checkout_com_payments</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**payment_type** | `string` | Required |
| attributes.**token** | `string` | Required |
| attributes.**session_id** | `string` | Optional |
| attributes.**success_url** | `string` | Optional |
| attributes.**failure_url** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**order** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new checkout.com payment:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/checkout_com_payments' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "checkout_com_payments",
    "attributes": {
      "payment_type": "token",
      "token": "tok_4gzeau5o2uqubbk6fufs3m7p54"
    },
    "relationships": {
      "order": {
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
    "type": "checkout_com_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/checkout_com_payments/xYZkjABcde"
    },
    "attributes": {
      "public_key": "pk_test_xxxx-yyyy-zzzz",
      "payment_type": "token",
      "token": "tok_4gzeau5o2uqubbk6fufs3m7p54",
      "session_id": "sid_y3oqhf46pyzuxjbcn2giaqnb44",
      "success_url": "http://commercelayer.dev/checkout_com/success",
      "failure_url": "http://commercelayer.dev/checkout_com/failure",
      "source_id": "src_nwd3m4in3hkuddfpjsaevunhdy",
      "customer_token": "cus_udst2tfldj6upmye2reztkmm4i",
      "redirect_uri": "https://api.checkout.com/3ds/pay_mbabizu24mvu3mela5njyhpit4",
      "payment_response": {
        "foo": "bar"
      },
      "mismatched_amounts": false,
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
          "self": "https://yourdomain.commercelayer.io/api/checkout_com_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/checkout_com_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/checkout_com_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/checkout_com_payments/xYZkjABcde/payment_gateway"
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

