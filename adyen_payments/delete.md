---
description: How to delete an existing adyen payment via API
---

# Delete an adyen payment

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an adyen payment, send a `DELETE` request to the `/api/adyen_payments/:id` endpoint, where `id` is the id of the adyen payment that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/adyen_payments/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the adyen payment identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/adyen_payments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

