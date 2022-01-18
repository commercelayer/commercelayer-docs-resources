---
description: How to update an existing google geocoder via API
---

# Update a google geocoder

To [update](https://docs.commercelayer.io/developers/updating-resources) an existing google geocoder, send a `PATCH` request to the `/api/google_geocoders/:id` endpoint, where `id` is the ID of the resource that you want to update.

Here below the list of all the possible arguments that you can pass with the request body.

## Request

**PATCH** https://yourdomain.commercelayer.io**/api/google\_geocoders/:id**

### Arguments

| Body Parameter                   | Type     | Required |
| -------------------------------- | -------- | -------- |
| **type**                         | `string` | Required |
| **id**                           | `string` | Required |
| attributes.**name**              | `string` | Optional |
| attributes.**reference**         | `string` | Optional |
| attributes.**reference\_origin** | `string` | Optional |
| attributes.**metadata**          | `object` | Optional |
| attributes.**api\_key**          | `string` | Optional |

### Example

{% tabs %}
{% tab title="Request" %}
The following request updates the google geocoder identified by the ID "xYZkjABcde":

```javascript
curl -g -X PATCH \
  'https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "google_geocoders",
    "id": "xYZkjABcde",
    "attributes": {
      "reference": "ANY-EXTERNAL-REFEFERNCE"
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
    "type": "google_geocoders",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde"
    },
    "attributes": {
      "name": "Default geocoder",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "addresses": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde/relationships/addresses",
          "related": "https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde/addresses"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde/attachments"
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
