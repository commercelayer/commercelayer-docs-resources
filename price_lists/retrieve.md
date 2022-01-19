---
description: How to fetch a specific price list via API
---

# Retrieve a price list

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single price list, send a `GET` request to the `/api/price_lists/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/price_lists/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the price list identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde' \
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
    "type": "price_lists",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde"
    },
    "attributes": {
      "name": "EU Price list",
      "currency_code": "EUR",
      "tax_included": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "prices": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/prices",
          "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/prices"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/attachments"
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

