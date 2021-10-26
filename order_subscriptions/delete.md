---
description: How to delete an existing order subscription via API
---

# Delete an order subscription

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an order subscription, send a `DELETE` request to the `/api/order_subscriptions/:id` endpoint, where `id` is the id of the order subscription that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/order_subscriptions/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the order subscription identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/order_subscriptions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

