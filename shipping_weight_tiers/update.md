---
description: How to update an existing shipping weight tier via API
---

# Update a shipping weight tier

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing shipping weight tier, send a `PATCH` request to the `/api/shipping_weight_tiers/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/shipping_weight_tiers/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**name** | `string` | Optional |
| attributes.**up_to** | `float` | Optional |
| attributes.**price_amount_cents** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**shipping_method** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the shipping weight tier identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "shipping_weight_tiers",
    "id": "xYZkjABcde",
    "attributes": {
      "up_to": 20.5
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
    "type": "shipping_weight_tiers",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde"
    },
    "attributes": {
      "name": "Light shipping under 3kg",
      "up_to": 20.5,
      "price_amount_cents": 1000,
      "price_amount_float": 10.0,
      "formatted_price_amount": "€10,00",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "shipping_method": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/relationships/shipping_method",
          "related": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/shipping_method"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde/attachments"
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

