---
description: How to update an existing stripe payment via API
---

# Update a stripe payment

To [update](https://docs.commercelayer.io/developers/updating-resources) an existing stripe payment, send a `PATCH` request to the `/api/stripe_payments/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/stripe\_payments/:id**

### Arguments

| Body Parameter                   | Type                       | Required |
| -------------------------------- | -------------------------- | -------- |
| **type**                         | `string`                   | Required |
| **id**                           | `string`                   | Required |
| attributes.**options**           | `object`                   | Optional |
| attributes.**\_refresh**         | `boolean, value is 'true'` | Optional |
| attributes.**reference**         | `string`                   | Optional |
| attributes.**reference\_origin** | `string`                   | Optional |
| attributes.**metadata**          | `object`                   | Optional |
| relationships.**order**          | `object`                   | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the stripe payment identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "stripe_payments",
    "id": "xYZkjABcde",
    "attributes": {
      "options": {
        "customer": "cus_xxx",
        "payment_method": "pm_xxx"
      }
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning the updated resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "stripe_payments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde"
    },
    "attributes": {
      "client_secret": "pi_1234XXX_secret_5678YYY",
      "publishable_key": "pk_live_xxxx-yyyy-zzzz",
      "options": {
        "customer": "cus_xxx",
        "payment_method": "pm_xxx"
      },
      "payment_method": {
        "id": "pm_xxx"
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
          "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/relationships/order",
          "related": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/order"
        }
      },
      "payment_gateway": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/relationships/payment_gateway",
          "related": "https://yourdomain.commercelayer.io/api/stripe_payments/xYZkjABcde/payment_gateway"
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
