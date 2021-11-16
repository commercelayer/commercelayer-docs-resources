---
description: How to update an existing parcel via API
---

# Update a parcel

To <a href="https://docs.commercelayer.io/developers/updating-resources" target="_blank">update</a> an existing parcel, send a `PATCH` request to the `/api/parcels/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/parcels/:id**

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| **id**         | `string` | Required |
| attributes.**weight** | `float` | Optional |
| attributes.**unit_of_weight** | `string` | Optional |
| attributes.**eel_pfc** | `string` | Optional |
| attributes.**contents_type** | `string` | Optional |
| attributes.**contents_explanation** | `string` | Optional |
| attributes.**customs_certify** | `boolean` | Optional |
| attributes.**customs_signer** | `string` | Optional |
| attributes.**non_delivery_option** | `string` | Optional |
| attributes.**restriction_type** | `string` | Optional |
| attributes.**restriction_comments** | `string` | Optional |
| attributes.**customs_info_required** | `boolean` | Optional |
| attributes.**tracking_number** | `string` | Optional |
| attributes.**tracking_status** | `string` | Optional |
| attributes.**tracking_status_detail** | `string` | Optional |
| attributes.**tracking_status_updated_at** | `datetime` | Optional |
| attributes.**tracking_details** | `string` | Optional |
| attributes.**carrier_weight_oz** | `string` | Optional |
| attributes.**signed_by** | `string` | Optional |
| attributes.**incoterm** | `string` | Optional |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| relationships.**shipment** | `object` | Optional |
| relationships.**package** | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the parcel identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "parcels",
    "id": "xYZkjABcde",
    "attributes": {
      "weight": 1000.0
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning the updated resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "parcels",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde"
    },
    "attributes": {
      "number": "#1234/S/001/P/001",
      "weight": 1000.0,
      "unit_of_weight": "gr",
      "eel_pfc": "EEL",
      "contents_type": "merchandise",
      "contents_explanation": "",
      "customs_certify": false,
      "customs_signer": "John Doe",
      "non_delivery_option": "return",
      "restriction_type": "none",
      "restriction_comments": "",
      "customs_info_required": false,
      "shipping_label_url": "https://bucket.s3-us-west-2.amazonaws.com/files/postage_label/20180101/123.pdf",
      "shipping_label_file_type": "application/pdf",
      "shipping_label_size": "4x7",
      "shipping_label_resolution": "200",
      "tracking_number": "1Z4V2A000000000000",
      "tracking_status": "delivered",
      "tracking_status_detail": "arrived_at_destination",
      "tracking_status_updated_at": "2018-01-01T12:00:00.000Z",
      "tracking_details": "",
      "carrier_weight_oz": "42.32",
      "signed_by": "John Smith",
      "incoterm": "EXW",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "shipment": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/relationships/shipment",
          "related": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/shipment"
        }
      },
      "package": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/relationships/package",
          "related": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/package"
        }
      },
      "parcel_line_items": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/relationships/parcel_line_items",
          "related": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/parcel_line_items"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde/attachments"
        }
      }
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

