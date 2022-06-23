---
description: How to delete an existing price tier via API
---

# Delete a price tier

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a price tier, send a `DELETE` request to the `/api/price_tiers/:id` endpoint, where `id` is the id of the price tier that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/price_tiers/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the price tier identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/price_tiers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

