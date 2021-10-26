---
description: How to delete an existing parcel via API
---

# Delete a parcel

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a parcel, send a `DELETE` request to the `/api/parcels/:id` endpoint, where `id` is the id of the parcel that you want to delete.

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/parcels/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the parcel identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/parcels/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

