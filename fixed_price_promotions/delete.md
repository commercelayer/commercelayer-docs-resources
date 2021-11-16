---
description: How to delete an existing fixed price promotion via API
---

# Delete a fixed price promotion

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a fixed price promotion, send a `DELETE` request to the `/api/fixed_price_promotions/:id` endpoint, where `id` is the id of the fixed price promotion that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/fixed_price_promotions/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the fixed price promotion identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/fixed_price_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

