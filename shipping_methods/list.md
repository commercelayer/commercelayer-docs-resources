---
description: How to fetch a collection of shipping methods via API
---

# List all shipping methods

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of shipping methods, send a `GET` request to the `/api/shipping_methods` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/shipping_methods

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of shipping methods:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/shipping_methods/' \
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
      "type": "shipping_methods",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde"
      },
      "attributes": {
        "name": "Standard shipping",
        "disabled_at": "2018-01-01T12:00:00.000Z",
        "currency_code": "EUR",
        "price_amount_cents": 1000,
        "price_amount_float": 10.0,
        "formatted_price_amount": "€10,00",
        "free_over_amount_cents": 9900,
        "free_over_amount_float": 99.0,
        "formatted_free_over_amount": "€99,00",
        "price_amount_for_shipment_cents": 0,
        "price_amount_for_shipment_float": 0.0,
        "formatted_price_amount_for_shipment": "€0,00",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "market": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/market",
            "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/market"
          }
        },
        "shipping_zone": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_zone",
            "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_zone"
          }
        },
        "shipping_category": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/shipping_category",
            "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/shipping_category"
          }
        },
        "delivery_lead_time_for_shipment": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/delivery_lead_time_for_shipment",
            "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/delivery_lead_time_for_shipment"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 shipping_methods (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/shipping_methods?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/shipping_methods?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/shipping_methods?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of shipping methods can be sorted by the following attributes:

* `name`
* `disabled_at`
* `price_amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

