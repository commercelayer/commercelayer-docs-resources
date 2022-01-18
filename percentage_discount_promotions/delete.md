---
description: How to delete an existing percentage discount promotion via API
---

# Delete a percentage discount promotion

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a percentage discount promotion, send a `DELETE` request to the `/api/percentage_discount_promotions/:id` endpoint, where `id` is the id of the percentage discount promotion that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/percentage\_discount\_promotions/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the percentage discount promotion identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/percentage_discount_promotions/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
