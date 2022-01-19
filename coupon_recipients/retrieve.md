---
description: How to fetch a specific coupon recipient via API
---

# Retrieve a coupon recipient

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single coupon recipient, send a `GET` request to the `/api/coupon_recipients/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/coupon_recipients/:id</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the coupon recipient identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde' \
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
    "type": "coupon_recipients",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde"
    },
    "attributes": {
      "email": "john@example.com",
      "first_name": "John",
      "last_name": "Smith",
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
          "self": "https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde/relationships/customer",
          "related": "https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde/customer"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde/attachments"
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

