---
description: How to delete an existing klarna payment via API
---

# Delete a klarna payment

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a klarna payment, send a `DELETE` request to the `/api/klarna_payments/:id` endpoint, where `id` is the id of the klarna payment that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/klarna_payments/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the klarna payment identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/klarna_payments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

