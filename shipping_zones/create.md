---
description: How to create a shipping zone via API
---

# Create a shipping zone

To [create](https://docs.commercelayer.io/developers/creating-resources) a new shipping zone, send a `POST` request to the `/api/shipping_zones` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://yourdomain.commercelayer.io**/api/shipping\_zones**

### Arguments

| Body Parameter                           | Type     | Required |
| ---------------------------------------- | -------- | -------- |
| **type**                                 | `string` | Required |
| attributes.**name**                      | `string` | Required |
| attributes.**country\_code\_regex**      | `string` | Optional |
| attributes.**not\_country\_code\_regex** | `string` | Optional |
| attributes.**state\_code\_regex**        | `string` | Optional |
| attributes.**not\_state\_code\_regex**   | `string` | Optional |
| attributes.**zip\_code\_regex**          | `string` | Optional |
| attributes.**not\_zip\_code\_regex**     | `string` | Optional |
| attributes.**reference**                 | `string` | Optional |
| attributes.**reference\_origin**         | `string` | Optional |
| attributes.**metadata**                  | `object` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new shipping zone:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/shipping_zones' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "shipping_zones",
    "attributes": {
      "name": "Europe (main countries)"
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "shipping_zones",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/shipping_zones/xYZkjABcde"
    },
    "attributes": {
      "name": "Europe (main countries)",
      "country_code_regex": "AT|BE|BG|CZ|DK|EE|DE|HU|LV|LT",
      "not_country_code_regex": "AT|BE|BG|CZ|DK|EE|DE",
      "state_code_regex": "A[KLRZ]|C[AOT]|D[CE]|FL",
      "not_state_code_regex": "A[KLRZ]|C[AOT]",
      "zip_code_regex": "(?i)(JE1|JE2|JE3|JE4|JE5)",
      "not_zip_code_regex": "(?i)(JE1|JE2|JE3)",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/shipping_zones/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/shipping_zones/xYZkjABcde/attachments"
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
