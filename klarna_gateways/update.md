---
description: How to update an existing klarna gateway via API
---

# Update a klarna gateway

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing klarna gateway, send a `PATCH` request to the `/api/klarna_gateways/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/klarna_gateways/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**name** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| attributes.**country_code** | `string` | Optional |
| attributes.**api_key** | `string` | Optional |
| attributes.**api_secret** | `string` | Optional |
| relationships.**klarna_payments** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the klarna gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "klarna_gateways",
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

