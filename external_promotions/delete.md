---
description: How to delete an existing external promotion via API
---

# Delete an external promotion

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an external promotion, send a `DELETE` request to the `/api/external_promotions/:id` endpoint, where `id` is the id of the external promotion that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/external_promotions/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the external promotion identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/external_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

