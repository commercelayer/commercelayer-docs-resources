---
description: How to fetch a collection of line item options via API
---

# List all line item options

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of line item options, send a `GET` request to the `/api/line_item_options` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/line_item_options</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of line item options:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/line_item_options/' \
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
      "type": "line_item_options",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde"
      },
      "attributes": {
        "name": "Embossing",
        "quantity": 2,
        "currency_code": "EUR",
        "unit_amount_cents": 990,
        "unit_amount_float": 9.9,
        "formatted_unit_amount": "€9,90",
        "total_amount_cents": 1880,
        "total_amount_float": 18.8,
        "formatted_total_amount": "€18,80",
        "delay_hours": 48,
        "delay_days": 2,
        "options": {
          "embossing_text": "Happy Birthday!"
        },
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "line_item": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde/relationships/line_item",
            "related": "https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde/line_item"
          }
        },
        "sku_option": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde/relationships/sku_option",
            "related": "https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde/sku_option"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 line_item_options (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/line_item_options?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/line_item_options?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/line_item_options?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of line item options can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `total_amount_cents`
* `delay_hours`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

