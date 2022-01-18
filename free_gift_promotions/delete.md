---
description: How to delete an existing free gift promotion via API
---

# Delete a free gift promotion

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a free gift promotion, send a `DELETE` request to the `/api/free_gift_promotions/:id` endpoint, where `id` is the id of the free gift promotion that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/free\_gift\_promotions/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the free gift promotion identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/free_gift_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
