---
description: How to delete an existing line item via API
---

# Delete a line item

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a line item, send a `DELETE` request to the `/api/line_items/:id` endpoint, where `id` is the id of the line item that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/line_items/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the line item identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/line_items/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

