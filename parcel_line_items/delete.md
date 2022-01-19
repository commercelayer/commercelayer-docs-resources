---
description: How to delete an existing parcel line item via API
---

# Delete a parcel line item

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a parcel line item, send a `DELETE` request to the `/api/parcel_line_items/:id` endpoint, where `id` is the id of the parcel line item that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/parcel_line_items/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the parcel line item identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/parcel_line_items/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

