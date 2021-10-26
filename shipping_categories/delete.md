---
description: How to delete an existing shipping category via API
---

# Delete a shipping category

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a shipping category, send a `DELETE` request to the `/api/shipping_categories/:id` endpoint, where `id` is the id of the shipping category that you want to delete.

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/shipping_categories/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the shipping category identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/shipping_categories/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

