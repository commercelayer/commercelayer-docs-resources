---
description: How to update an existing delivery lead time via API
---

# Update a delivery lead time

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing delivery lead time, send a `PATCH` request to the `/api/delivery_lead_times/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io<b>/api/delivery_lead_times/:id</b>

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**min_hours** | `integer` | Optional |
| attributes.**max_hours** | `integer` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**stock_location** | `object` | Optional |
| relationships.**shipping_method** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the delivery lead time identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "delivery_lead_times",
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
    "type": "delivery_lead_times",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde"
    },
    "attributes": {
      "min_hours": 48,
      "max_hours": 72,
      "min_days": 2,
      "max_days": 3,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "stock_location": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/relationships/stock_location",
          "related": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/stock_location"
        }
      },
      "shipping_method": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/relationships/shipping_method",
          "related": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/shipping_method"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/delivery_lead_times/xYZkjABcde/attachments"
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

