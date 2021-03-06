---
description: How to delete an existing tax rule via API
---

# Delete a tax rule

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a tax rule, send a `DELETE` request to the `/api/tax_rules/:id` endpoint, where `id` is the id of the tax rule that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/tax_rules/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the tax rule identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/tax_rules/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

