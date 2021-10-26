---
description: How to delete an existing SKU option via API
---

# Delete a SKU option

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a SKU option, send a `DELETE` request to the `/api/sku_options/:id` endpoint, where `id` is the id of the SKU option that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/sku_options/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the SKU option identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/sku_options/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

