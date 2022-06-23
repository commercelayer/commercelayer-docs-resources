---
description: How to fetch a collection of customer addresses via API
---

# List all customer addresses

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of customer addresses, send a `GET` request to the `/api/customer_addresses` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/customer_addresses</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of customer addresses:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_addresses/' \
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
      "type": "customer_addresses",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde"
      },
      "attributes": {
        "name": "John Smith, 2883 Geraldine Lane Apt.23, 10013 New York NY (US) (212) 646-338-1228",
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
            "self": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/relationships/customer",
            "related": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/customer"
          }
        },
        "address": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/relationships/address",
            "related": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/address"
          }
        },
        "events": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/relationships/events",
            "related": "https://yourdomain.commercelayer.io/api/customer_addresses/xYZkjABcde/events"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 customer_addresses (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/customer_addresses?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/customer_addresses?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/customer_addresses?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of customer addresses can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

