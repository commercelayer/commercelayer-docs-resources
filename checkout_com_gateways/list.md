---
description: How to fetch a collection of checkout.com gateways via API
---

# List all checkout.com gateways

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of checkout.com gateways, send a `GET` request to the `/api/checkout_com_gateways` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/checkout_com_gateways

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of checkout.com gateways:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/checkout_com_gateways/' \
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
      "type": "checkout_com_gateways",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde"
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
        "webhook_endpoint_id": "xxxx-yyyy-zzzz",
        "webhook_endpoint_secret": "xxxx-yyyy-zzzz",
        "webhook_endpoint_url": "https://core.commercelayer.co/webhook_callbacks/checkout_com_gateways/xxxxx"
      },
      "relationships": {
        "payment_methods": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde/relationships/payment_methods",
            "related": "https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde/payment_methods"
          }
        },
        "checkout_com_payments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde/relationships/checkout_com_payments",
            "related": "https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde/checkout_com_payments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 checkout_com_gateways (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/checkout_com_gateways?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/checkout_com_gateways?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/checkout_com_gateways?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of checkout.com gateways can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

