---
description: How to fetch a collection of shipments via API
---

# List all shipments

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of shipments, send a `GET` request to the `/api/shipments` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io<b>/api/shipments</b>

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of shipments:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/shipments/' \
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
      "type": "shipments",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde"
      },
      "attributes": {
        "number": "#1234/S/001",
        "status": "draft",
        "currency_code": "EUR",
        "cost_amount_cents": 1000,
        "cost_amount_float": 10.0,
        "formatted_cost_amount": "€10,00",
        "skus_count": 2,
        "selected_rate_id": "rate_f89e4663c3ed47ee94d37763f6d21d54",
        "rates": [
          {
            "id": "rate_f89e4663c3ed47ee94d37763f6d21d54",
            "rate": "45.59",
            "carrier": "DHLExpress",
            "service": "MedicalExpress"
          }
        ],
        "purchase_error_code": "SHIPMENT.POSTAGE.FAILURE",
        "purchase_error_message": "Account not allowed for this service.",
        "get_rates_errors": [
          {
            "carrier": "DHLExpress",
            "message": "to_address.postal_code: Shorter than minimum length 3",
            "type": "rate_error"
          }
        ],
        "get_rates_started_at": "2018-01-01T12:00:00.000Z",
        "get_rates_completed_at": "2018-01-01T12:00:00.000Z",
        "purchase_started_at": "2018-01-01T12:00:00.000Z",
        "purchase_completed_at": "2018-01-01T12:00:00.000Z",
        "purchase_failed_at": "2018-01-01T12:00:00.000Z",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "order": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/order",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/order"
          }
        },
        "shipping_category": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/shipping_category",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/shipping_category"
          }
        },
        "stock_location": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/stock_location",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/stock_location"
          }
        },
        "origin_address": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/origin_address",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/origin_address"
          }
        },
        "shipping_address": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/shipping_address",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/shipping_address"
          }
        },
        "shipping_method": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/shipping_method",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/shipping_method"
          }
        },
        "delivery_lead_time": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/delivery_lead_time",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/delivery_lead_time"
          }
        },
        "shipment_line_items": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/shipment_line_items",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/shipment_line_items"
          }
        },
        "stock_line_items": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/stock_line_items",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/stock_line_items"
          }
        },
        "stock_transfers": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/stock_transfers",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/stock_transfers"
          }
        },
        "available_shipping_methods": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/available_shipping_methods",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/available_shipping_methods"
          }
        },
        "carrier_accounts": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/carrier_accounts",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/carrier_accounts"
          }
        },
        "parcels": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/parcels",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/parcels"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/attachments"
          }
        },
        "events": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/relationships/events",
            "related": "https://yourdomain.commercelayer.io/api/shipments/xYZkjABcde/events"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 shipments (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/shipments?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/shipments?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/shipments?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

Remember that when you fetch a list of resources you get <a href="https://docs.commercelayer.io/developers/pagination" target="_blank">paginated</a> result.

### Sortable attributes

The list of shipments can be <a href="https://docs.commercelayer.io/developers/sorting-results" target="_blank">sorted</a> by the following attributes:

* `status`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

