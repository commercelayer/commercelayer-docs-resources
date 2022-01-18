---
description: How to fetch a collection of manual tax calculators via API
---

# List all manual tax calculators

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of manual tax calculators, send a `GET` request to the `/api/manual_tax_calculators` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/manual\_tax\_calculators**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of manual tax calculators:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/manual_tax_calculators/' \
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
      "type": "manual_tax_calculators",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde"
      },
      "attributes": {
        "name": "Personal tax calculator",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "tax_categories": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/relationships/tax_categories",
            "related": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/tax_categories"
          }
        },
        "markets": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/relationships/markets",
            "related": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/markets"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/attachments"
          }
        },
        "tax_rules": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/relationships/tax_rules",
            "related": "https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde/tax_rules"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 manual_tax_calculators (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/manual_tax_calculators?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/manual_tax_calculators?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/manual_tax_calculators?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of manual tax calculators can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
