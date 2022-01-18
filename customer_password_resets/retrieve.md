---
description: How to fetch a specific customer password reset via API
---

# Retrieve a customer password reset

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single customer password reset, send a `GET` request to the `/api/customer_password_resets/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/customer\_password\_resets/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the customer password reset identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_password_resets/xYZkjABcde' \
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
    "type": "customer_password_resets",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/customer_password_resets/xYZkjABcde"
    },
    "attributes": {
      "customer_email": "john@example.com",
      "reset_password_token": "xhFfkmfybsLxzaAP6xcs",
      "reset_password_at": "2018-01-01T12:00:00.000Z",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "customer": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_password_resets/xYZkjABcde/relationships/customer",
          "related": "https://yourdomain.commercelayer.io/api/customer_password_resets/xYZkjABcde/customer"
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
