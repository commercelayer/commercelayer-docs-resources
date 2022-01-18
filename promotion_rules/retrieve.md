---
description: How to fetch a specific promotion rule via API
---

# Retrieve a promotion rule

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single promotion rule, send a `GET` request to the `/api/promotion_rules/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/promotion\_rules/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the promotion rule identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/promotion_rules/xYZkjABcde' \
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
    "type": "promotion_rules",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/promotion_rules/xYZkjABcde"
    },
    "attributes": {
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "promotion": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/promotion_rules/xYZkjABcde/relationships/promotion",
          "related": "https://yourdomain.commercelayer.io/api/promotion_rules/xYZkjABcde/promotion"
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
