---
description: How to fetch the organization via API
---

# Retrieve the organization

To [fetch](https://docs.commercelayer.io/developers/fetching-resources) the organization, send a `GET` request to the `/api/organization` endpoint.

## Request

**GET** https://yourdomain.commercelayer.io**/api/organization**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the organization in scope:

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/organization/' \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "organizations",
    "attributes": {
      "name": "The Blue Brand",
      "slug": "the-blue-brand",
      "domain": "the-blue-brand.commercelayer.io",
      "support_phone": "+01 30800857",
      "support_email": "support@bluebrand.com",
      "logo_url": "https://bluebrand.com/img/logo.svg",
      "favicon_url": "https://bluebrand.com/img/favicon.ico",
      "primary_color": "#C8984E",
      "contrast_color": "#FFFFCC",
      "gtm_id": "GTM-5FJXX6",
      "gtm_id_test": "GTM-5FJXX7",
      "discount_disabled": false,
      "account_disabled": false,
      "acceptance_disabled": false,
      "max_concurrent_promotions": 10,
      "max_concurrent_imports": 30,
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}
