---
description: How to delete an existing SKU via API
---

# Delete a SKU

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a SKU, send a `DELETE` request to the `/api/skus/:id` endpoint, where `id` is the id of the SKU that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/skus/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the SKU identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/skus/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

