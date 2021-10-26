---
description: How to create a google geocoder via API
---

# Create a google geocoder

To <a href="https://docs.commercelayer.io/developers/creating-resources" target="_blank">create</a> a new google geocoder, send a `POST` request to the `/api/google_geocoders` endpoint, passing the resource arguments in the request body.

## Request

**POST** https://<i></i>yourdomain.commercelayer.io/api/google_geocoders

### Arguments

| Body Parameter | Type     | Required |
| -------------- | -------- | -------- |
| **type**       | `string` | Required |
| attributes.**name** | `string` | Required |
| attributes.**reference** | `string` | Optional |
| attributes.**reference_origin** | `string` | Optional |
| attributes.**metadata** | `object` | Optional |
| attributes.**api_key** | `string` | Required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new google geocoder:

```javascript
curl -g -X POST \
  'https://yourdomain.commercelayer.io/api/google_geocoders' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "google_geocoders",
    "attributes": {
      "name": "Default geocoder",
      "api_key": "xxxx-yyyy-zzzz"
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

