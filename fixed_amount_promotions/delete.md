---
description: How to delete an existing fixed amount promotion via API
---

# Delete a fixed amount promotion

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a fixed amount promotion, send a `DELETE` request to the `/api/fixed_amount_promotions/:id` endpoint, where `id` is the id of the fixed amount promotion that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/fixed\_amount\_promotions/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the fixed amount promotion identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/fixed_amount_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
