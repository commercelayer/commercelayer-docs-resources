---
description: How to fetch a collection of adyen gateways via API
---

# List all adyen gateways

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of adyen gateways, send a `GET` request to the `/api/adyen_gateways` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/adyen_gateways

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of adyen gateways:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/adyen_gateways/' \
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
      "type": "adyen_gateways",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/adyen_gateways/xYZkjABcde"
      },
      "attributes": {
        "name": "US payment gateway",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        },
        "live_url_prefix": "1797a841fbb37ca7-AdyenDemo"
      },
      "relationships": {
        "payment_methods": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/adyen_gateways/xYZkjABcde/relationships/payment_methods",
            "related": "https://yourdomain.commercelayer.io/api/adyen_gateways/xYZkjABcde/payment_methods"
          }
        },
        "adyen_payments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/adyen_gateways/xYZkjABcde/relationships/adyen_payments",
            "related": "https://yourdomain.commercelayer.io/api/adyen_gateways/xYZkjABcde/adyen_payments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 adyen_gateways (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/adyen_gateways?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/adyen_gateways?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/adyen_gateways?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of adyen gateways can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`
* `merchant_account`

