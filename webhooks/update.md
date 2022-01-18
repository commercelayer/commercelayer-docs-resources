---
description: How to update an existing webhook via API
---

# Update a webhook

To [update](https://docs.commercelayer.io/developers/updating-resources) an existing webhook, send a `PATCH` request to the `/api/webhooks/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/webhooks/:id**

### Arguments

| Body Parameter                    | Type                       | Required |
| --------------------------------- | -------------------------- | -------- |
| **type**                          | `string`                   | Required |
| **id**                            | `string`                   | Required |
| attributes.**name**               | `string`                   | Optional |
| attributes.**topic**              | `string`                   | Optional |
| attributes.**callback\_url**      | `string`                   | Optional |
| attributes.**include\_resources** | `array`                    | Optional |
| attributes.**\_reset\_circuit**   | `boolean, value is 'true'` | Optional |
| attributes.**reference**          | `string`                   | Optional |
| attributes.**reference\_origin**  | `string`                   | Optional |
| attributes.**metadata**           | `object`                   | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the webhook identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "webhooks",
    "id": "xYZkjABcde",
    "attributes": {
      "include_resources": [
        "customer",
        "shipping_address",
        "billing_address"
      ]
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
    "type": "webhooks",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde"
    },
    "attributes": {
      "name": "myorg-orders.place",
      "topic": "orders.place",
      "callback_url": "https://yourapp.com/webhooks",
      "include_resources": [
        "customer",
        "shipping_address",
        "billing_address"
      ],
      "circuit_state": "closed",
      "circuit_failure_count": 5,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "last_event_callbacks": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde/relationships/last_event_callbacks",
          "related": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde/last_event_callbacks"
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
