---
description: How to update an existing external gateway via API
---

# Update an external gateway

To [update](https://docs.commercelayer.io/developers/updating-resources) an existing external gateway, send a `PATCH` request to the `/api/external_gateways/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/external\_gateways/:id**

### Arguments

| Body Parameter                   | Type     | Required |
| -------------------------------- | -------- | -------- |
| **type**                         | `string` | Required |
| **id**                           | `string` | Required |
| attributes.**name**              | `string` | Optional |
| attributes.**reference**         | `string` | Optional |
| attributes.**reference\_origin** | `string` | Optional |
| attributes.**metadata**          | `object` | Optional |
| attributes.**authorize\_url**    | `string` | Optional |
| attributes.**capture\_url**      | `string` | Optional |
| attributes.**void\_url**         | `string` | Optional |
| attributes.**refund\_url**       | `string` | Optional |
| attributes.**token\_url**        | `string` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the external gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "external_gateways",
    "id": "xYZkjABcde",
    "attributes": {
      "reference": "ANY-EXTERNAL-REFEFERNCE"
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
    "type": "external_gateways",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde"
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
      "shared_secret": "xxxx-yyyy-zzzz",
      "authorize_url": "https://external_gateway.com/authorize",
      "capture_url": "https://external_gateway.com/capture",
      "void_url": "https://external_gateway.com/void",
      "refund_url": "https://external_gateway.com/refund",
      "token_url": "https://external_gateway.com/token"
    },
    "relationships": {
      "payment_methods": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde/relationships/payment_methods",
          "related": "https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde/payment_methods"
        }
      },
      "external_payments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde/relationships/external_payments",
          "related": "https://yourdomain.commercelayer.io/api/external_gateways/xYZkjABcde/external_payments"
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
