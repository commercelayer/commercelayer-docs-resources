---
description: How to delete an existing line item option via API
---

# Delete a line item option

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a line item option, send a `DELETE` request to the `/api/line_item_options/:id` endpoint, where `id` is the id of the line item option that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/line\_item\_options/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the line item option identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/line_item_options/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
