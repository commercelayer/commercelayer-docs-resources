---
description: How to delete an existing shipping weight tier via API
---

# Delete a shipping weight tier

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a shipping weight tier, send a `DELETE` request to the `/api/shipping_weight_tiers/:id` endpoint, where `id` is the id of the shipping weight tier that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/shipping_weight_tiers/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the shipping weight tier identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/shipping_weight_tiers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

