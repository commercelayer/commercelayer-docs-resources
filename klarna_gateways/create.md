---
description: How to create a klarna gateway via API
---

# Create a klarna gateway

To [create](https://docs.commercelayer.io/developers/creating-resources) a new klarna gateway, send a `POST` request to the `/api/klarna_gateways` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/klarna\_gateways**

### Arguments

| Body Parameter                     | Type     | Required |
| ---------------------------------- | -------- | -------- |
| **type**                           | `string` | Required |
| attributes.**name**                | `string` | Required |
| attributes.**reference**           | `string` | Optional |
| attributes.**reference\_origin**   | `string` | Optional |
| attributes.**metadata**            | `object` | Optional |
| attributes.**country\_code**       | `string` | Required |
| attributes.**api\_key**            | `string` | Required |
| attributes.**api\_secret**         | `string` | Required |
| relationships.**klarna\_payments** | `array`  | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new klarna gateway:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/klarna_gateways' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "klarna_gateways",
    "attributes": {
      "name": "US payment gateway",
      "country_code": "EU",
      "api_key": "xxxx-yyyy-zzzz",
      "api_secret": "xxxx-yyyy-zzzz"
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
    "type": "klarna_gateways",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde"
    },
    "attributes": {
      "name": "US payment gateway",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "payment_methods": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/relationships/payment_methods",
          "related": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/payment_methods"
        }
      },
      "klarna_payments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/relationships/klarna_payments",
          "related": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/klarna_payments"
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
