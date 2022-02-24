---
description: How to create a percentage discount promotion via API
---

# Create a percentage discount promotion

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new percentage discount promotion, send a `POST` request to the `/api/percentage_discount_promotions` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/percentage_discount_promotions</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**currency_code** | `string` | Required, unless inherited by market |
| attributes.**starts_at** | `datetime` | Required |
| attributes.**expires_at** | `datetime` | Required |
| attributes.**total_usage_limit** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| attributes.**percentage** | `integer` | Required |
| relationships.**market** | `object` | Optional |
| relationships.**promotion_rules** | `array` | Optional |
| relationships.**order_amount_promotion_rule** | `object` | Optional |
| relationships.**sku_list_promotion_rule** | `object` | Optional |
| relationships.**coupon_codes_promotion_rule** | `object` | Optional |
| relationships.**sku_list** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new percentage discount promotion:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/percentage_discount_promotions' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "percentage_discount_promotions",
    "attributes": {
      "name": "Personal promotion",
      "currency_code": "EUR",
      "starts_at": "2018-01-01T12:00:00.000Z",
      "expires_at": "2018-01-02T12:00:00.000Z",
      "total_usage_limit": 5,
      "percentage": 10
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
    "type": "percentage_discount_promotions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde"
    },
    "attributes": {
      "name": "Personal promotion",
      "currency_code": "EUR",
      "starts_at": "2018-01-01T12:00:00.000Z",
      "expires_at": "2018-01-02T12:00:00.000Z",
      "total_usage_limit": 5,
      "total_usage_count": 2,
      "active": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      },
      "percentage": 10
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/market"
        }
      },
      "promotion_rules": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/promotion_rules",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/promotion_rules"
        }
      },
      "order_amount_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/order_amount_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/order_amount_promotion_rule"
        }
      },
      "sku_list_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/sku_list_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/sku_list_promotion_rule"
        }
      },
      "coupon_codes_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/coupon_codes_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/coupon_codes_promotion_rule"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/attachments"
        }
      },
      "sku_list": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/sku_list",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/sku_list"
        }
      },
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde/skus"
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

