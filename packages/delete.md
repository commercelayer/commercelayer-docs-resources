---
description: How to delete an existing package via API
---

# Delete a package

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a package, send a `DELETE` request to the `/api/packages/:id` endpoint, where `id` is the id of the package that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/packages/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the package identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/packages/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

