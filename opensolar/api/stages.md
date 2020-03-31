# Stages

{% api-method method="get" host="https://api.openx.solar" path="/stages/all" %}

{% api-method method="get" host="https://api.openx.solar" path="/stages" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
curl -X GET "http://api2.openx.solar/stages?index=1"
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="index" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "Number": 1,
  "FriendlyName": "Engagement",
  "Name": "RFP Development",
  "Activities": [
    "[Solar Developer] Analyse parameters, create financial model (proforma)",
    "[Host] & [Solar Developer] engage [Legal] & begin scoping site for planning constraints and opportunities (viability analysis)",
    "[Solar Developer] Create RFP (‘Request For Proposal’)",
    "Simple: Automatic calculation (eg. Sunroof style)",
    "Complex: Public project with 3rd party RFP consultant (independent engineer)",
    "[Originator][Solar Developer][Offtaker] Post project for RFP",
    "[Beneficiary/Host] Define and select RFP developer.",
    "[Investor] First angel investment option (high risk)",
    "Allow ‘time banking’ as sweat equity, monetized as tokenized capital or shadow stock"
  ],
  "StateTrigger": [
    "Issue an RFP",
    "Letter of Intent or MOU between originator and developer"
  ],
  "BreachCondition": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/stages/promote" %}
{% api-method-summary %}
Promote a project's stage
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

{% api-method-parameter name="index" type="number" required=true %}

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

