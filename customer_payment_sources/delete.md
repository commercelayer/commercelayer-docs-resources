---
description: How to delete an existing customer payment source via API
---

# Delete a customer payment source

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a customer payment source, send a `DELETE` request to the `/api/customer_payment_sources/:id` endpoint, where `id` is the id of the customer payment source that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/customer\_payment\_sources/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the customer payment source identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/customer_payment_sources/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
