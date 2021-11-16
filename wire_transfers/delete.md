---
description: How to delete an existing wire transfer via API
---

# Delete a wire transfer

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a wire transfer, send a `DELETE` request to the `/api/wire_transfers/:id` endpoint, where `id` is the id of the wire transfer that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/wire_transfers/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the wire transfer identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/wire_transfers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

