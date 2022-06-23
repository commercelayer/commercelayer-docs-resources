---
description: How to fetch a collection of price volume tiers via API
---

# List all price volume tiers

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of price volume tiers, send a `GET` request to the `/api/price_volume_tiers` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/price_volume_tiers</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of price volume tiers:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/price_volume_tiers/' \
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
      "type": "price_volume_tiers",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/price_volume_tiers/xYZkjABcde"
      },
      "attributes": {
        "name": "six pack",
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
        "price": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/price_volume_tiers/xYZkjABcde/relationships/price",
            "related": "https://yourdomain.commercelayer.io/api/price_volume_tiers/xYZkjABcde/price"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/price_volume_tiers/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/price_volume_tiers/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 price_volume_tiers (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/price_volume_tiers?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/price_volume_tiers?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/price_volume_tiers?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of price volume tiers can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `up_to`
* `price_amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

