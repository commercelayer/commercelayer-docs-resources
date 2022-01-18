---
description: How to fetch a collection of customer groups via API
---

# List all customer groups

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of customer groups, send a `GET` request to the `/api/customer_groups` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/customer\_groups**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of customer groups:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_groups/' \
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
      "type": "customer_groups",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde"
      },
      "attributes": {
        "name": "VIP",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "customers": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/customers",
            "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/customers"
          }
        },
        "markets": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/markets",
            "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/markets"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 customer_groups (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/customer_groups?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/customer_groups?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/customer_groups?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of customer groups can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
