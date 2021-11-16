---
description: How to update an existing coupon via API
---

# Update a coupon

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing coupon, send a `PATCH` request to the `/api/coupons/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/coupons/:id**

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**code** | `string` | Optional |
| attributes.**usage_limit** | `integer` | Optional |
| attributes.**recipient_email** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**promotion_rule** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the coupon identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "coupons",
    "id": "xYZkjABcde",
    "attributes": {
      "recipient_email": "john@example.com"
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

