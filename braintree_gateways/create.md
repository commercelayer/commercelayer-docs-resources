---
description: How to create a braintree gateway via API
---

# Create a braintree gateway

To [create](https://docs.commercelayer.io/developers/creating-resources) a new braintree gateway, send a `POST` request to the `/api/braintree_gateways` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/braintree\_gateways**

### Arguments

| Body Parameter                        | Type     | Required |
| ------------------------------------- | -------- | -------- |
| **type**                              | `string` | Required |
| attributes.**name**                   | `string` | Required |
| attributes.**reference**              | `string` | Optional |
| attributes.**reference\_origin**      | `string` | Optional |
| attributes.**metadata**               | `object` | Optional |
| attributes.**merchant\_account\_id**  | `string` | Required |
| attributes.**merchant\_id**           | `string` | Required |
| attributes.**public\_key**            | `string` | Required |
| attributes.**private\_key**           | `string` | Required |
| attributes.**descriptor\_name**       | `string` | Optional |
| attributes.**descriptor\_phone**      | `string` | Optional |
| attributes.**descriptor\_url**        | `string` | Optional |
| relationships.**braintree\_payments** | `array`  | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new braintree gateway:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/braintree_gateways' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "braintree_gateways",
    "attributes": {
      "name": "US payment gateway",
      "merchant_account_id": "xxxx-yyyy-zzzz",
      "merchant_id": "xxxx-yyyy-zzzz",
      "public_key": "xxxx-yyyy-zzzz",
      "private_key": "xxxx-yyyy-zzzz"
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
    "type": "braintree_gateways",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/braintree_gateways/xYZkjABcde"
    },
    "attributes": {
      "name": "US payment gateway",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "descriptor_name": "company*productabc1234",
      "descriptor_phone": "3125551212",
      "descriptor_url": "company.com",
      "webhook_endpoint_url": "https://core.commercelayer.co/webhook_callbacks/braintree_gateways/xxxxx"
    },
    "relationships": {
      "payment_methods": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/braintree_gateways/xYZkjABcde/relationships/payment_methods",
          "related": "https://yourdomain.commercelayer.io/api/braintree_gateways/xYZkjABcde/payment_methods"
        }
      },
      "braintree_payments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/braintree_gateways/xYZkjABcde/relationships/braintree_payments",
          "related": "https://yourdomain.commercelayer.io/api/braintree_gateways/xYZkjABcde/braintree_payments"
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
