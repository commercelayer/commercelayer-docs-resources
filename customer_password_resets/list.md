---
description: How to fetch a collection of customer password resets via API
---

# List all customer password resets

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of customer password resets, send a `GET` request to the `/api/customer_password_resets` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/customer\_password\_resets**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of customer password resets:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_password_resets/' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a paginated collection of resource objects:

```javascript
{
  "data": [
    {
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
    },
    {
      "other": "... 9 customer_password_resets (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/customer_password_resets?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/customer_password_resets?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/customer_password_resets?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of customer password resets can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
