---
description: How to delete an existing shipping method tier via API
---

# Delete a shipping method tier

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a shipping method tier, send a `DELETE` request to the `/api/shipping_method_tiers/:id` endpoint, where `id` is the id of the shipping method tier that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/shipping_method_tiers/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the shipping method tier identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/shipping_method_tiers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

