---
description: How to update an existing gift card via API
---

# Update a gift card

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing gift card, send a `PATCH` request to the `/api/gift_cards/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

{% page-ref page="../../updating-resources.md" %}

## Request

**PATCH** https://<i></i>yourdomain.commercelayer.io/api/gift_cards/:id

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**currency_code** | `string` | Optional |
| attributes.**balance_cents** | `integer` | Optional |
| attributes.**balance_max_cents** | `string` | Optional |
| attributes.**single_use** | `boolean` | Optional |
| attributes.**rechargeable** | `boolean` | Optional |
| attributes.**image_url** | `string` | Optional |
| attributes.**expires_at** | `datetime` | Optional |
| attributes.**recipient_email** | `string` | Optional |
| attributes.**_purchase** | `boolean, value is 'true'` | Optional |
| attributes.**_activate** | `boolean, value is 'true'` | Optional |
| attributes.**_deactivate** | `boolean, value is 'true'` | Optional |
| attributes.**_balance_change_cents** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**market** | `object` | Optional |
| relationships.**gift_card_recipient** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the gift card identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "gift_cards",
    "id": "xYZkjABcde",
    "attributes": {
      "balance_max_cents": "100000"
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
    "type": "gift_cards",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde"
    },
    "attributes": {
      "status": "draft",
      "code": "32db311a-75d9-4c17-9e34-2be220137ad6",
      "currency_code": "EUR",
      "initial_balance_cents": 15000,
      "initial_balance_float": 150.0,
      "formatted_initial_balance": "€150,00",
      "balance_cents": 15000,
      "balance_float": 150.0,
      "formatted_balance": "€150,00",
      "balance_max_cents": "100000",
      "balance_max_float": 1000.0,
      "formatted_balance_max": "€1000,00",
      "balance_log": [
        {
          "date": "2019-12-23T12:00:00.000Z",
          "amount_cents": -10000
        },
        {
          "date": "2020-02-01T12:00:00.000Z",
          "amount_cents": 5000
        }
      ],
      "single_use": false,
      "rechargeable": true,
      "image_url": "https://img.yourdomain.com/gift_cards/32db311a.png",
      "expires_at": "2018-01-01T12:00:00.000Z",
      "recipient_email": "john@example.com",
      "_balance_change_cents": -5000,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/market"
        }
      },
      "gift_card_recipient": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/relationships/gift_card_recipient",
          "related": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/gift_card_recipient"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/gift_cards/xYZkjABcde/attachments"
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

