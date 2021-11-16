---
description: How to delete an existing stripe gateway via API
---

# Delete a stripe gateway

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a stripe gateway, send a `DELETE` request to the `/api/stripe_gateways/:id` endpoint, where `id` is the id of the stripe gateway that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/stripe_gateways/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the stripe gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/stripe_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

