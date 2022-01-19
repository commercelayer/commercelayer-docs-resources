---
description: How to fetch a specific shipping category via API
---

# Retrieve a shipping category

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single shipping category, send a `GET` request to the `/api/shipping_categories/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/shipping_categories/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the shipping category identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde' \
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
    "type": "shipping_categories",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde"
    },
    "attributes": {
      "name": "Merchandise",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "skus": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/relationships/skus",
          "related": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/skus"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde/attachments"
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

