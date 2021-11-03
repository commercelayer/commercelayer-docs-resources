---
description: How to fetch a collection of taxjar accounts via API
---

# List all taxjar accounts

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of taxjar accounts, send a `GET` request to the `/api/taxjar_accounts` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/taxjar_accounts

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of taxjar accounts:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/taxjar_accounts/' \
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
      "type": "taxjar_accounts",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde"
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
            "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/tax_categories",
            "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/tax_categories"
          }
        },
        "markets": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/markets",
            "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/markets"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 taxjar_accounts (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/taxjar_accounts?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/taxjar_accounts?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/taxjar_accounts?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of taxjar accounts can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
* `api_key`

