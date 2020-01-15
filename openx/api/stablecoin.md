---
description: Stablecoin related endpoints
---

# Stablecoin

{% api-method method="get" host="https://api.openx.solar" path="/stablecoin/get" %}
{% api-method-summary %}
Get Stablecoin
{% endapi-method-summary %}

{% api-method-description %}
This endpoint fetches test stablecoin  
  
**curl -X GET "http://api2.openx.solar/stablecoin/get?seed=SA5DXUTRWHQXOHPISTRLPH55NIUOSV2GB5NDTOSZ7H33KOK2TYYU556O&amount=1&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&username=john"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="amount" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/anchor/get" %}
{% api-method-summary %}
Get AnchorUSD
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

