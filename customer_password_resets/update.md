---
description: How to update an existing customer password reset via API
---

# Update a customer password reset

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing customer password reset, send a `PATCH` request to the `/api/customer_password_resets/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://<i></i>yourdomain.commercelayer.io/api/customer_password_resets/:id

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**customer_password** | `string` | Optional |
| attributes.**_reset_password_token** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the customer password reset identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/customer_password_resets/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "customer_password_resets",
    "id": "xYZkjABcde",
    "attributes": {
      "customer_password": "secret"
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

