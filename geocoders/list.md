---
description: How to fetch a collection of geocoders via API
---

# List all geocoders

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a collection of geocoders, send a `GET` request to the `/api/geocoders` endpoint.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/geocoders

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of geocoders:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/geocoders/' \
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
      "type": "geocoders",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/geocoders/xYZkjABcde"
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
            "self": "https://yourdomain.commercelayer.io/api/geocoders/xYZkjABcde/relationships/addresses",
            "related": "https://yourdomain.commercelayer.io/api/geocoders/xYZkjABcde/addresses"
          }
        },
        "attachments": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/geocoders/xYZkjABcde/relationships/attachments",
            "related": "https://yourdomain.commercelayer.io/api/geocoders/xYZkjABcde/attachments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 geocoders (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/geocoders?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/geocoders?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/geocoders?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of geocoders can be sorted by the following attributes:

* `name`
* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

