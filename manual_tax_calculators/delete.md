---
description: How to delete an existing manual tax calculator via API
---

# Delete a manual tax calculator

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a manual tax calculator, send a `DELETE` request to the `/api/manual_tax_calculators/:id` endpoint, where `id` is the id of the manual tax calculator that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/manual\_tax\_calculators/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the manual tax calculator identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/manual_tax_calculators/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
