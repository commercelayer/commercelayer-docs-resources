---
description: How to delete an existing checkout.com gateway via API
---

# Delete a checkout.com gateway

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a checkout.com gateway, send a `DELETE` request to the `/api/checkout_com_gateways/:id` endpoint, where `id` is the id of the checkout.com gateway that you want to delete.

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/checkout_com_gateways/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the checkout.com gateway identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/checkout_com_gateways/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

