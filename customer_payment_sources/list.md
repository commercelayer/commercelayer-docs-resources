---
description: How to fetch a collection of customer payment sources via API
---

# List all customer payment sources

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of customer payment sources, send a `GET` request to the `/api/customer_payment_sources` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/customer_payment_sources

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of customer payment sources:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_payment_sources/' \
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
      "type": "customer_payment_sources",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde"
      },
      "attributes": {
        "name": "XXXX-XXXX-XXXX-1111",
        "customer_token": "cus_xxxyyyzzz",
        "payment_source_token": "pm_xxxyyyzzz",
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
            "self": "https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde/relationships/customer",
            "related": "https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde/customer"
          }
        },
        "payment_source": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde/relationships/payment_source",
            "related": "https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde/payment_source"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 customer_payment_sources (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/customer_payment_sources?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/customer_payment_sources?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/customer_payment_sources?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of customer payment sources can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

