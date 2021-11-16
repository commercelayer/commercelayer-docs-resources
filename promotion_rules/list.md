---
description: How to fetch a collection of promotion rules via API
---

# List all promotion rules

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of promotion rules, send a `GET` request to the `/api/promotion_rules` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/promotion_rules**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of promotion rules:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/promotion_rules/' \
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
    },
    {
      "other": "... 9 promotion_rules (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/promotion_rules?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/promotion_rules?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/promotion_rules?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of promotion rules can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

