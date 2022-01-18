---
description: How to delete an existing inventory stock location via API
---

# Delete an inventory stock location

To [delete](https://docs.commercelayer.io/developers/deleting-resources) an inventory stock location, send a `DELETE` request to the `/api/inventory_stock_locations/:id` endpoint, where `id` is the id of the inventory stock location that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/inventory\_stock\_locations/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the inventory stock location identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/inventory_stock_locations/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
