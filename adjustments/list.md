---
description: How to fetch a collection of adjustments via API
---

# List all adjustments

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of adjustments, send a `GET` request to the `/api/adjustments` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/adjustments

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of adjustments:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/adjustments/' \
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
      "type": "adjustments",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/adjustments/xYZkjABcde"
      },
      "attributes": {
        "name": "Additional service",
        "currency_code": "EUR",
        "amount_cents": 1500,
        "amount_float": 15.0,
        "formatted_amount": "€15,00",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 adjustments (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/adjustments?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/adjustments?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/adjustments?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of adjustments can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `currency_code`
* `amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

