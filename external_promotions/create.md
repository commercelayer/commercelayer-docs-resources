---
description: How to create an external promotion via API
---

# Create an external promotion

To [create](https://docs.commercelayer.io/developers/creating-resources) a new external promotion, send a `POST` request to the `/api/external_promotions` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/external\_promotions**

### Arguments

| Body Parameter                                   | Type       | Required                             |
| ------------------------------------------------ | ---------- | ------------------------------------ |
| **type**                                         | `string`   | Required                             |
| attributes.**name**                              | `string`   | Required                             |
| attributes.**currency\_code**                    | `string`   | Required, unless inherited by market |
| attributes.**starts\_at**                        | `datetime` | Required                             |
| attributes.**expires\_at**                       | `datetime` | Required                             |
| attributes.**total\_usage\_limit**               | `integer`  | Required                             |
| attributes.**reference**                         | `string`   | Optional                             |
| attributes.**reference\_origin**                 | `string`   | Optional                             |
| attributes.**metadata**                          | `object`   | Optional                             |
| attributes.**promotion\_url**                    | `string`   | Required                             |
| relationships.**market**                         | `object`   | Required, unless in scope            |
| relationships.**promotion\_rules**               | `array`    | Optional                             |
| relationships.**order\_amount\_promotion\_rule** | `object`   | Optional                             |
| relationships.**sku\_list\_promotion\_rule**     | `object`   | Optional                             |
| relationships.**coupon\_codes\_promotion\_rule** | `object`   | Optional                             |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new external promotion:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/external_promotions' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "external_promotions",
    "attributes": {
      "name": "Personal promotion",
      "currency_code": "EUR",
      "starts_at": "2018-01-01T12:00:00.000Z",
      "expires_at": "2018-01-02T12:00:00.000Z",
      "total_usage_limit": 5,
      "promotion_url": "https://external_promotion.yourbrand.com"
    },
    "relationships": {
      "market": {
        "data": {
          "type": "markets",
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
    "type": "external_promotions",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde"
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
      "promotion_url": "https://external_promotion.yourbrand.com"
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/market"
        }
      },
      "promotion_rules": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/promotion_rules",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/promotion_rules"
        }
      },
      "order_amount_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/order_amount_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/order_amount_promotion_rule"
        }
      },
      "sku_list_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/sku_list_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/sku_list_promotion_rule"
        }
      },
      "coupon_codes_promotion_rule": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/coupon_codes_promotion_rule",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/coupon_codes_promotion_rule"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde/attachments"
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
