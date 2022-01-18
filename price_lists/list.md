---
description: How to fetch a collection of price lists via API
---

# List all price lists

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a collection of price lists, send a `GET` request to the `/api/price_lists` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/price\_lists**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of price lists:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/price_lists/' \
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
      "type": "price_lists",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde"
      },
      "attributes": {
        "name": "EU Price list",
        "currency_code": "EUR",
        "tax_included": true,
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "prices": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/prices",
            "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/prices"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 price_lists (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/price_lists?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/price_lists?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/price_lists?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get [paginated](https://docs.commercelayer.io/developers/pagination) result.

### Sortable attributes

The list of price lists can be [sorted](https://docs.commercelayer.io/developers/sorting-results) by the following attributes:

* `name`
* `currency_code`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
