# API documentation

{% api-method method="post" host="https://apidocs.openx.solar" path="/token" %}
{% api-method-summary %}
Get Access Token
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch a token that can be then used to access all endpoints
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="pwhash" type="boolean" required=true %}
The pwhash of the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
  "Token": "fKQfVnJkYLtSYSRfvVHepADaHVxtJdkX"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



