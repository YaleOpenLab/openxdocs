# Stages

{% api-method method="get" host="https://api.openx.solar" path="/stages/all" %}
{% api-method-summary %}
Get all stages
{% endapi-method-summary %}

{% api-method-description %}
  
**curl -X GET "https://api2.openx.solar/stages/all"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
[
  {
    "Number": 0,
    "FriendlyName": "Handshake",
    "Name": "Idea Consolidation",
    "Activities": [
      "[Originator] proposes project and either secures or agrees to serve as [Solar Developer]. NOTE: Originator is the community leader or catalyst for the project, they may opt to serve as the solar developer themselves, or pass that responsibility off, going forward we will use solar developer to represent the interest of both.",
      "[Solar Developer] creates general estimation of project (eg. with an automatic calculation through Google Project Sunroof, PV) ",
      "If [Originator]/[Solar Developer] is not landowner [Host] states legal ownership of site (hard proof is optional at this stage)"
    ],
    "StateTrigger": [
      "Matching of originator with receiver, and mutual approval/intention of interest."
    ],
    "BreachCondition": null
  },
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
  },
  {
    "Number": 2,
    "FriendlyName": "Quotes",
    "Name": "Actions",
    "Activities": [
      "[Solar Developer][Beneficiary/Offtaker][Legal] PPA model negotiation.",
      "[Originator][Beneficiary]  Compare quotes from bidders: ",
      "[Engineering Procurement and Construction] (labor)",
      "[Vendors] (Hardware)",
      "[Insurers]",
      "[Issuer]",
      "[Intermediary Portal]",
      "[Originator/Receiver] Begin negotiation with [Utility]",
      "[Solar Developer] checks whether site upgrades are necessary.",
      "[Solar Developer][Host] Prepare submission for permitting and planning",
      "[Investor] Angel incorporation (less risk)"
    ],
    "StateTrigger": [
      "Selection of quotes and vendors",
      "Necessary identification of entities: Installers and offtaker"
    ],
    "BreachCondition": null
  },
  {
    "Number": 3,
    "FriendlyName": "Signing",
    "Name": "Contract Execution",
    "Activities": [
      "[Solar Developer] pays [Legal] for PPA finalization.",
      "[Solar Developer][Host] Signs site Lease with landowner.",
      "[Solar Developer] OR [Issuer] signs Offering Agreement with [Intermediary Portal].",
      "[Solar Developer][Beneficiary] selects and signs contracts with: ",
      "[Engineering Procurement and Construction] (labor)",
      "[Vendors] (Hardware)",
      "[Insurers]",
      "[Issuer] OR [Intermediary Portal]",
      "[Offtaker] OR [Solar Developer][Engineering, Procurement and Construction] sign vendor/developer EPC Contracts",
      "[Solar Developer][Offtaker] signs PPA/Offtake Agreement",
      "[Investor] 2nd stage of eligible funding",
      "[Solar Developer][Beneficiary] makes downpayment to [Engineering Procurement and Construction] (labor)",
      "[Investor] Profile with risk "
    ],
    "StateTrigger": [
      "Execution of contracts - Sign!"
    ],
    "BreachCondition": null
  },
  {
    "Number": 4,
    "FriendlyName": "The Raise",
    "Name": "Finance and Capitalization",
    "Activities": [
      "[Issuer] engages [Intermediary Portal] to develop Form C or prospectus",
      "[Intermediary Portal] lists [Issuer] project",
      "[Originator][Solar Developer][Offtaker] market the crowdfunded offering",
      "[Investors] Commit capital to the project",
      "[Intermediary Portal] closes offering and disburses capital from Escrow account to [Issuers]",
      "If [Issuer] is not also [Solar Developer] then [Issuer] passes funds to [Solar Developer] "
    ],
    "StateTrigger": [
      "Project account receives funds that cover the raise amount. Raise amount: normally includes both project capital expenditure (i.e. hardware and labor) and ongoing Operation & Management costs"
    ],
    "BreachCondition": null
  },
  {
    "Number": 5,
    "FriendlyName": "Construction",
    "Name": "Payments and Construction",
    "Activities": [
      "[Solar Developer] coordinates installation dates and arrangements with [Host][Off-takers]",
      "[Solar Developer] OR [Engineering, Procurement and Construction] take delivery of equipment from [Vendor]",
      "[Utility] issues conditional interconnection",
      "[Solar Developer] schedules installation with [Engineering, Procurement and Construction]",
      "[Engineering, Procurement and Construction] completes installation.",
      "[Solar Developer] pays [Engineering, Procurement and Construction] for substantial completion of the project.",
      "[Insurers] verifies policy, [Solar Developer] pays [Insurers]",
      "[Investor] role?"
    ],
    "StateTrigger": [
      "Installation reaches substantial completion",
      "IoT devices detect energy generation"
    ],
    "BreachCondition": null
  },
  {
    "Number": 6,
    "FriendlyName": "Interconnection",
    "Name": "Contract Execution",
    "Activities": [
      "[Solar Developer] coordinates with [Engineering Procurement and Construction] to schedule interconnection dates with [Utility] ",
      "[Engineering, Procurement and Construction] submits ‘as-built’ drawings to City/County Inspectors and schedules interconnection with [Utility]",
      "[Solar Developer] schedules City/County Building Inspector visit",
      "[Utility] visits site for witness test",
      "[Utility] places project in service "
    ],
    "StateTrigger": [
      "[Utility] places project in service"
    ],
    "BreachCondition": null
  },
  {
    "Number": 7,
    "FriendlyName": "Legacy",
    "Name": "Operation and Management",
    "Activities": [
      "[Solar Developer] hires OR becomes [Manager]",
      "[Manager] hires [Operations & Maintenance] provider",
      "[Manager] sets up billing system and issues monthly bills to [Offtaker] and collects payment on bills",
      "[Manager] monitors for breaches of payment or contract, other indentures, force majeure or adverse conditions [see below for Breach Conditions]",
      "[Manager] files annual taxes",
      "[Manager] handles annual true-up on net-metering payments",
      "[Manager] makes annual cash distributions and issues 1099-DIV to [Investors] or coordinates share repurchase from [Investors]",
      "If applicable, [Manager] executes flip between [Solar Developer] ownership interest and [Tax equity investor]",
      "[Manager] OR [Operations & Maintenance] monitors system performance and coordinates with [Off-takers] to schedule routine maintenance",
      "[Manager] OR [Operations & Maintenance] coordinates with [Engineering, Procurement and Construction] to change inverters or purchase replacements from [Vendors] as needed.",
      "[Investors] can engage in secondary market (i.e. re-selling its securities). "
    ],
    "StateTrigger": [
      "[Investors] reach preferred return rate, or Power Purchase Agreement stipulates ownership flip date or conditions "
    ],
    "BreachCondition": [
      "[Offtaker] fails to make $/kWh payments after X period of time due. "
    ]
  },
  {
    "Number": 8,
    "FriendlyName": "Handoff",
    "Name": "Ownership Flip",
    "Activities": [
      "[Beneficiary/Offtakers] Payments accrue to cover the [Investor] principle (i.e. total raised amount)",
      "Escrow account (eg. capital account) pays off principle to [Investor]"
    ],
    "StateTrigger": [
      "[Beneficiary] (eg. Host, Holding)  becomes full legal owner of physical assets",
      "[Investors] exit the project"
    ],
    "BreachCondition": null
  },
  {
    "Number": 9,
    "FriendlyName": "End of Life",
    "Name": "Disposal",
    "Activities": [
      "[IoT] Solar equipment is generating below a productivity threshold, or shows general malfunction",
      "[Beneficiaries][Developers] dispose of the equipment to a recycling program",
      "[Developer/Recycler] Certifies equipment is received"
    ],
    "StateTrigger": [
      "Project termination",
      "Wallet terminations"
    ],
    "BreachCondition": null
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/stages" %}
{% api-method-summary %}
Get a specific stage
{% endapi-method-summary %}

{% api-method-description %}
  
**curl -X GET "http://api2.openx.solar/stages?index=1"**
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

```
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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

