---
description: How to delete an existing paypal gateway via API
---

# Delete a paypal gateway

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a paypal gateway, send a `DELETE` request to the `/api/paypal_gateways/:id` endpoint, where `id` is the id of the paypal gateway that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/paypal\_gateways/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the paypal gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/paypal_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
