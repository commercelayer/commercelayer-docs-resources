---
description: How to fetch a specific google geocoder via API
---

# Retrieve a google geocoder

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) a single google geocoder, send a `GET` request to the `/api/google_geocoders/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/google\_geocoders/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the google geocoder identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

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
