---
description: How to update an existing coupon codes promotion rule via API
---

# Update a coupon codes promotion rule

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing coupon codes promotion rule, send a `PATCH` request to the `/api/coupon_codes_promotion_rules/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/coupon_codes_promotion_rules/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**promotion** | `object` | Optional |
| relationships.**coupons** | `array` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the coupon codes promotion rule identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "coupon_codes_promotion_rules",
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
    "type": "coupon_codes_promotion_rules",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde"
    },
    "attributes": {
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "promotion": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde/relationships/promotion",
          "related": "https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde/promotion"
        }
      },
      "coupons": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde/relationships/coupons",
          "related": "https://yourdomain.commercelayer.io/api/coupon_codes_promotion_rules/xYZkjABcde/coupons"
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

