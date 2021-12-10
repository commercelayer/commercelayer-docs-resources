---
description: How to fetch a collection of coupons via API
---

# List all coupons

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of coupons, send a `GET` request to the `/api/coupons` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/coupons</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of coupons:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/coupons/' \
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
      "type": "coupons",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde"
      },
      "attributes": {
        "code": "04371af2-70b3-48d7-8f4e-316b374224c3",
        "customer_single_use": false,
        "usage_limit": 50,
        "usage_count": 20,
        "recipient_email": "john@example.com",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "promotion_rule": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde/relationships/promotion_rule",
            "related": "https://yourdomain.commercelayer.io/api/coupons/xYZkjABcde/promotion_rule"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 coupons (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/coupons?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/coupons?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/coupons?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of coupons can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `code`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

