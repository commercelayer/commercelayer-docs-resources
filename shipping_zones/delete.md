---
description: How to delete an existing shipping zone via API
---

# Delete a shipping zone

To [delete](https://docs.commercelayer.io/developers/deleting-resources) a shipping zone, send a `DELETE` request to the `/api/shipping_zones/:id` endpoint, where `id` is the id of the shipping zone that you want to delete.

## Request

**DELETE** https://yourdomain.commercelayer.io**/api/shipping\_zones/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the shipping zone identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/shipping_zones/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}
