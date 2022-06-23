---
description: How to fetch a specific price tier via API
---

# Retrieve a price tier

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single price tier, send a `GET` request to the `/api/price_tiers/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/price_tiers/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the price tier identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "price_tiers",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde"
    },
    "attributes": {
      "name": "six pack",
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
      "price": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/relationships/price",
          "related": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/price"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde/attachments"
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

