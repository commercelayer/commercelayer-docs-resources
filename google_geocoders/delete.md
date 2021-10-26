---
description: How to delete an existing google geocoder via API
---

# Delete a google geocoder

To <a href="https://docs.commercelayer.io/developers/deleting-resources" target="_blank">delete</a> a google geocoder, send a `DELETE` request to the `/api/google_geocoders/:id` endpoint, where `id` is the id of the google geocoder that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io/api/google_geocoders/:id

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the google geocoder identified by the ID "xYZkjABcde":

```javascript
curl -g -X DELETE \
  'https://yourdomain.commercelayer.io/api/google_geocoders/xYZkjABcde' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

