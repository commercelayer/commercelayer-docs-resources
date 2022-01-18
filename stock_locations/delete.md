---
description: How to delete an existing stock location via API
---

# Delete a stock location

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a stock location, send a `DELETE` request to the `/api/stock_locations/:id` endpoint, where `id` is the id of the stock location that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/stock\_locations/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the stock location identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/stock_locations/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
