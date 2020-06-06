---
description: This pages describes the APIs associated with games.
---

# Games APIs

{% api-method method="get" host="https://gira.asankov.org" path="/v1/games" %}
{% api-method-summary %}
Get Games
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch all games
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
Authentication token to track down who wants to see the games.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Games successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "games": [
        {
            "id": "123",
            "name": "Assassin's Creed",
        }, 
        {
            "id": "124",
            "name": "Assassin's Creed II",
        },
    ]
    
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



{% api-method method="get" host="https://gira.asankov.org" path="/v1/games/{id}" %}
{% api-method-summary %}
Get Game By ID
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch a game by ID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the game to fetch.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
Authentication token to track down who wants to see the game.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Game successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "id": "123",
    "name": "Assassin's Creed",
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

{% api-method method="post" host="https://gira.asankov.org" path="/v1/games" %}
{% api-method-summary %}
Create Game
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create a game.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-token" type="string" required=true %}
Authentication token to track down who wants to create a game.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Name of the game to be created.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Game successfully created.
{% endapi-method-response-example-description %}

```
{
    "id": "123",
    "name": "Assassin's Creed",
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Name not sent as part of the request.
{% endapi-method-response-example-description %}

```
{
    "error": "'name' is required parameter"
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

