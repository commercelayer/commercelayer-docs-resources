---
description: How to delete an existing inventory return location via API
---

# Delete an inventory return location

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an inventory return location, send a `DELETE` request to the `/api/inventory_return_locations/:id` endpoint, where `id` is the id of the inventory return location that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/inventory_return_locations/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the inventory return location identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/inventory_return_locations/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

