---
description: How to delete an existing price list via API
---

# Delete a price list

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a price list, send a `DELETE` request to the `/api/price_lists/:id` endpoint, where `id` is the id of the price list that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/price\_lists/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the price list identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/price_lists/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
