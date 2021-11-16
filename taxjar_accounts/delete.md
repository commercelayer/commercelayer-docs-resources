---
description: How to delete an existing taxjar account via API
---

# Delete a taxjar account

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a taxjar account, send a `DELETE` request to the `/api/taxjar_accounts/:id` endpoint, where `id` is the id of the taxjar account that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/taxjar_accounts/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the taxjar account identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/taxjar_accounts/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

