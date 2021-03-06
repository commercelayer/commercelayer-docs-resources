---
description: How to delete an existing klarna gateway via API
---

# Delete a klarna gateway

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a klarna gateway, send a `DELETE` request to the `/api/klarna_gateways/:id` endpoint, where `id` is the id of the klarna gateway that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/klarna_gateways/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the klarna gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/klarna_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

