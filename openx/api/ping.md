---
description: A common endpoint to ping the platform and see if its up
---

# Ping

{% api-method method="get" host="https://api.openx.solar" path="/ping" %}
{% api-method-summary %}
Ping the platform
{% endapi-method-summary %}

{% api-method-description %}
  
**curl -X GET "https://api.openx.solar/ping"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "Code": 200,
  "Status": "OK"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

