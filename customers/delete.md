---
description: How to delete an existing customer via API
---

# Delete a customer

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a customer, send a `DELETE` request to the `/api/customers/:id` endpoint, where `id` is the id of the customer that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/customers/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the customer identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/customers/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

