# Particle

{% api-method method="get" host="https://api.openx.solar" path="/particle/devices" %}
{% api-method-summary %}
Get all devices
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/devices?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&productInfo=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/productinfo" %}
{% api-method-summary %}
Get Product Info
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/productinfo?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&productInfo=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="productInfo" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/deviceinfo" %}
{% api-method-summary %}
Get Device Info
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="deviceId" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/deviceping" %}
{% api-method-summary %}
Ping Device
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/deviceping?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="deviceId" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/devicesignal" %}
{% api-method-summary %}
Signal Device
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/devicesignal?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah&signal=on**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="signal" type="boolean" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/getdeviceid" %}
{% api-method-summary %}
Get Device ID
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/getdeviceid?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&serialNumber=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="serialNumber" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/diag/last" %}
{% api-method-summary %}
Get last diagnostic
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/diag/last?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="deviceId" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/diag/all" %}
{% api-method-summary %}
Get all diagnostics
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/diag/all?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="deviceId" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/user/info" %}
{% api-method-summary %}
Get User Info
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**http://api2.openx.solar/particle/user/info?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/particle/sims" %}
{% api-method-summary %}
Get sim card info
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET"**http://api2.openx.solar/particle/sims?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="accessToken" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

