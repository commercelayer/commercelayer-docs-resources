---
description: How to create an adjustment via API
---

# Create an adjustment

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new adjustment, send a `POST` request to the `/api/adjustments` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io<b>/api/adjustments</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**currency_code** | `string` | Required |
| attributes.**amount_cents** | `integer` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new adjustment:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/adjustments' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "adjustments",
    "attributes": {
      "name": "Additional service",
      "currency_code": "EUR",
      "amount_cents": 1500
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
    "type": "adjustments",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/adjustments/xYZkjABcde"
    },
    "attributes": {
      "name": "Additional service",
      "currency_code": "EUR",
      "amount_cents": 1500,
      "amount_float": 15.0,
      "formatted_amount": "€15,00",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

