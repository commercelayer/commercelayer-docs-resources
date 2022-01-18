---
description: How to fetch a collection of order validation rules via API
---

# List all order validation rules

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of order validation rules, send a `GET` request to the `/api/order_validation_rules` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/order\_validation\_rules**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of order validation rules:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/order_validation_rules/' \
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
      "type": "order_validation_rules",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/order_validation_rules/xYZkjABcde"
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
            "self": "https://yourdomain.commercelayer.io/api/order_validation_rules/xYZkjABcde/relationships/market",
            "related": "https://yourdomain.commercelayer.io/api/order_validation_rules/xYZkjABcde/market"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 order_validation_rules (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/order_validation_rules?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/order_validation_rules?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/order_validation_rules?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of order validation rules can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
