---
description: How to delete an existing in stock subscription via API
---

# Delete an in stock subscription

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an in stock subscription, send a `DELETE` request to the `/api/in_stock_subscriptions/:id` endpoint, where `id` is the id of the in stock subscription that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/in_stock_subscriptions/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the in stock subscription identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/in_stock_subscriptions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

