---
description: How to delete an existing inventory model via API
---

# Delete an inventory model

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an inventory model, send a `DELETE` request to the `/api/inventory_models/:id` endpoint, where `id` is the id of the inventory model that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/inventory_models/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the inventory model identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

