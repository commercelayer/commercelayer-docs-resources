---
description: How to delete an existing coupon recipient via API
---

# Delete a coupon recipient

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a coupon recipient, send a `DELETE` request to the `/api/coupon_recipients/:id` endpoint, where `id` is the id of the coupon recipient that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io<b>/api/coupon_recipients/:id</b>

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the coupon recipient identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/coupon_recipients/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

