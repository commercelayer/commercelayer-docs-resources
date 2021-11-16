---
description: How to fetch a specific customer group via API
---

# Retrieve a customer group

To <a href="https://docs.commercelayer.io/developers/fetching-resources" target="_blank">fetch</a> a single customer group, send a `GET` request to the `/api/customer_groups/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

## Request

**GET** https://yourdomain.commercelayer.io**/api/customer_groups/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the customer group identified by the id "xYZkjABcde":

```javascript
curl -g -X GET \
  'https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde' \
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
    "type": "customer_groups",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde"
    },
    "attributes": {
      "name": "VIP",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "customers": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/customers",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/customers"
        }
      },
      "markets": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/markets",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/markets"
        }
      },
      "attachments": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/attachments",
          "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/attachments"
        }
      }
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

