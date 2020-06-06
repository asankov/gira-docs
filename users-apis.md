---
description: This pages describes the APIs associated with users.
---

# Users APIs

{% api-method method="get" host="https://gira.asankov.org" path="/v1/users" %}
{% api-method-summary %}
Get User
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get the authenticated user
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
Authentication token associated with the user.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "user": {
        "id": "123",
        "username": "user",
        "email": "user@mail.com"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No token present in request.
{% endapi-method-response-example-description %}

```
{
    "error": "Unauthorized"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



