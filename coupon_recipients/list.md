---
description: How to fetch a collection of coupon recipients via API
---

# List all coupon recipients

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of coupon recipients, send a `GET` request to the `/api/coupon_recipients` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/coupon_recipients</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of coupon recipients:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/coupon_recipients/' \
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
    },
    {
      "other": "... 9 coupon_recipients (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/coupon_recipients?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/coupon_recipients?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/coupon_recipients?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of coupon recipients can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

