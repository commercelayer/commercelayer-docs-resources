---
description: How to delete an existing avalara account via API
---

# Delete an avalara account

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an avalara account, send a `DELETE` request to the `/api/avalara_accounts/:id` endpoint, where `id` is the id of the avalara account that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/avalara_accounts/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the avalara account identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/avalara_accounts/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

