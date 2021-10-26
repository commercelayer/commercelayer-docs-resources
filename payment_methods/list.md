---
description: How to fetch a collection of payment methods via API
---

# List all payment methods

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of payment methods, send a `GET` request to the `/api/payment_methods` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/payment_methods

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of payment methods:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/payment_methods/' \
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
      "type": "payment_methods",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde"
      },
      "attributes": {
        "payment_source_type": "CreditCard",
        "name": "Credit Card",
        "disabled_at": "2018-01-01T12:00:00.000Z",
        "price_amount_cents": 0,
        "price_amount_float": 0.0,
        "formatted_price_amount": "€0,00",
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
            "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/market",
            "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/market"
          }
        },
        "payment_gateway": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/payment_gateway",
            "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/payment_gateway"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/payment_methods/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 payment_methods (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/payment_methods?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/payment_methods?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/payment_methods?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of payment methods can be sorted by the following attributes:

* `payment_source_type`
* `disabled_at`
* `price_amount_cents`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

