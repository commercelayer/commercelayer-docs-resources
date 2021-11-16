---
description: How to create a coupon via API
---

# Create a coupon

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new coupon, send a `POST` request to the `/api/coupons` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/coupons</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**code** | `string` | Required |
| attributes.**usage_limit** | `integer` | Required |
| attributes.**recipient_email** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**promotion_rule** | `object` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new coupon:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/coupons' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "coupons",
    "attributes": {
      "code": "04371af2-70b3-48d7-8f4e-316b374224c3",
      "usage_limit": 50
    },
    "relationships": {
      "promotion_rule": {
        "data": {
          "type": "coupon_codes_promotion_rules",
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
    "type": "coupons",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde"
    },
    "attributes": {
      "code": "04371af2-70b3-48d7-8f4e-316b374224c3",
      "usage_limit": 50,
      "usage_count": 20,
      "recipient_email": "john@example.com",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde/relationships/promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde/promotion_rule"
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

