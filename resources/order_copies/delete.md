---
description: How to delete an existing order copy via API
---

# Delete an order copy

To delete an order copy, send a `DELETE` request to the `/api/order_copies/:id` endpoint, where `id` is the id of the order copy that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/order_copies/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the order copy identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/order_copies/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

