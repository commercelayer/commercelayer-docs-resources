---
description: How to delete an existing shipping method via API
---

# Delete a shipping method

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a shipping method, send a `DELETE` request to the `/api/shipping_methods/:id` endpoint, where `id` is the id of the shipping method that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/shipping_methods/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the shipping method identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/shipping_methods/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

