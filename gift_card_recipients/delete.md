---
description: How to delete an existing gift card recipient via API
---

# Delete a gift card recipient

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a gift card recipient, send a `DELETE` request to the `/api/gift_card_recipients/:id` endpoint, where `id` is the id of the gift card recipient that you want to delete.

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/gift_card_recipients/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the gift card recipient identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/gift_card_recipients/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

