---
description: How to fetch a collection of shipping method tiers via API
---

# List all shipping method tiers

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of shipping method tiers, send a `GET` request to the `/api/shipping_method_tiers` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/shipping_method_tiers</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of shipping method tiers:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/shipping_method_tiers/' \
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
      "type": "shipping_method_tiers",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde"
      },
      "attributes": {
        "name": "Light shipping under 3kg",
        "up_to": 20.5,
        "price_amount_cents": 1000,
        "price_amount_float": 10.0,
        "formatted_price_amount": "€10,00",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "shipping_method": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde/relationships/shipping_method",
            "related": "https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde/shipping_method"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 shipping_method_tiers (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/shipping_method_tiers?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/shipping_method_tiers?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/shipping_method_tiers?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of shipping method tiers can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `up_to`
* `price_amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

