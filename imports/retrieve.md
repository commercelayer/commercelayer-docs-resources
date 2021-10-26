---
description: How to fetch a specific import via API
---

# Retrieve an import

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single import, send a `GET` request to the `/api/imports/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://<i></i>yourdomain.commercelayer.io/api/imports/:id

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the import identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/imports/xYZkjABcde' \
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
    "type": "imports",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/imports/xYZkjABcde"
    },
    "attributes": {
      "resource_type": "skus",
      "parent_resource_id": "1234",
      "status": "in_progress",
      "started_at": "2018-01-01T12:00:00.000Z",
      "completed_at": "2018-01-01T12:00:00.000Z",
      "interrupted_at": "2018-01-01T12:00:00.000Z",
      "inputs": [
        {
          "code": "ABC",
          "name": "Foo"
        },
        {
          "code": "DEF",
          "name": "Bar"
        }
      ],
      "inputs_size": 300,
      "errors_count": 30,
      "warnings_count": 1,
      "destroyed_count": 99,
      "processed_count": 270,
      "errors_log": {
        "ABC": {
          "name": [
            "has already been taken"
          ]
        }
      },
      "warnings_log": {
        "ABC": [
          "could not be deleted"
        ]
      },
      "cleanup_records": true,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

