---
description: How to delete an existing SKU list item via API
---

# Delete a SKU list item

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a SKU list item, send a `DELETE` request to the `/api/sku_list_items/:id` endpoint, where `id` is the id of the SKU list item that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/sku\_list\_items/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the SKU list item identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/sku_list_items/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
