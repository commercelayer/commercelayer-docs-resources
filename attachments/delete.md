---
description: How to delete an existing attachment via API
---

# Delete an attachment

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> an attachment, send a `DELETE` request to the `/api/attachments/:id` endpoint, where `id` is the id of the attachment that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/attachments/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the attachment identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/attachments/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

