---
description: How to fetch the application via API
---

# Retrieve the application

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) the application, send a `GET` request to the `/api/application` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/application**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the application in scope:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/application/' \
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
    "type": "applications",
    "attributes": {
      "name": "My app",
      "kind": "sales-channel",
      "public_access": "true",
      "redirect_uri": "https://bluebrand.com/img/logo.svg",
      "scopes": "market:all market:9 market:122 market:6 stock_location:6 stock_location:33",
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
