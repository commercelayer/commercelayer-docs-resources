---
description: How to fetch a specific klarna gateway via API
---

# Retrieve a klarna gateway

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single klarna gateway, send a `GET` request to the `/api/klarna_gateways/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/klarna\_gateways/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the klarna gateway identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde' \
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
    "type": "klarna_gateways",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde"
    },
    "attributes": {
      "name": "US payment gateway",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "payment_methods": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/relationships/payment_methods",
          "related": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/payment_methods"
        }
      },
      "klarna_payments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/relationships/klarna_payments",
          "related": "https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde/klarna_payments"
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
