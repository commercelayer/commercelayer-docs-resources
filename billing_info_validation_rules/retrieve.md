---
description: How to fetch a specific billing info validation rule via API
---

# Retrieve a billing info validation rule

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single billing info validation rule, send a `GET` request to the `/api/billing_info_validation_rules/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/billing_info_validation_rules/:id

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the billing info validation rule identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde' \
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
    "type": "billing_info_validation_rules",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde"
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
      "market": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde/relationships/market",
          "related": "https://yourdomain.commercelayer.io/api/billing_info_validation_rules/xYZkjABcde/market"
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

