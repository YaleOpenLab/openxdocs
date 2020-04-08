# Projects

{% api-method method="post" host="https://api.openx.solar" path="/project/insert" %}
{% api-method-summary %}
Insert new project
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="Stage" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="Metadata" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="Location" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="TotalValue" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="PanelSize" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="get" host="https://api.openx.solar" path="/project/all" %}
{% api-method-summary %}
Get all Projects
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**https://api2.openx.solar/project/all?username=admin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft**"**
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

```text
[
  {
    "Index": 1,
    "TotalValue": 4000,
    "Lock": false,
    "LockPwd": "",
    "Chain": "stellar",
    "OneTimeUnlock": "",
    "AmountOwed": 0,
    "Reputation": 0,
    "Votes": 0,
    "OwnershipShift": 0,
    "StageData": null,
    "StageChecklist": null,
    "InvestorMap": null,
    "SeedInvestorMap": null,
    "WaterfallMap": null,
    "RecipientIndex": -1,
    "OriginatorIndex": -1,
    "GuarantorIndex": -1,
    "ContractorIndex": -1,
    "InvestorIndices": null,
    "SeedInvestorIndices": null,
    "DateInitiated": "",
    "DateFunded": "",
    "DateLastPaid": 0,
    "AuctionType": "",
    "InvestmentType": "munibond",
    "PaybackPeriod": 2419200000000000,
    "Stage": 3,
    "InvestorAssetCode": "",
    "DebtAssetCode": "",
    "PaybackAssetCode": "",
    "SeedAssetCode": "",
    "SeedInvestmentFactor": 0,
    "SeedInvestmentCap": 0,
    "EscrowPubkey": "",
    "EscrowLock": false,
    "MoneyRaised": 0,
    "SeedMoneyRaised": 0,
    "EstimatedAcquisition": 0,
    "BalLeft": 0,
    "AdminFlagged": false,
    "FlaggedBy": 0,
    "UserFlaggedBy": null,
    "Reports": 0,
    "TellerUrl": "",
    "BrokerUrl": "mqtt.openx.solar",
    "TellerPublishTopic": "opensolartest",
    "Metadata": "Aibonito Pilot Project",
    "Name": "5kW Solar at FabIDEAS Coop - Pilot 1",
    "City": "Aibonito",
    "State": "Puerto Rico",
    "Country": "USA",
    "Panel Size": "50 x 100W",
    "Image": "",
    "Interest Rate": 0,
    "Investment Cap": 0,
    "Amount Self Funded": 0,
    "Main Developer Index": 0,
    "Developer Indices": null,
    "Contractor Fee": 0,
    "Originator Fee": 0,
    "Developer Fee": null,
    "Location": "Puerto Rico",
    "Donation Type": "Grant",
    "Originator": "Martin Wainstein",
    "Description": "5kW solar to be owned by the FabIDEAS Community Cooperative in Aibonito. The Coop is part of the Institution Nueva Escuela (INE), and will host a Fab Lab manufacturing montessori school supplies.",
    "Bullet1": "Powering a unique social entrepreneurship model through a local cooperative",
    "Bullet2": "Power purchase agreement tied to the standard local Aibonito tariff",
    "Bullet3": "Pay-to-own solar model for the coop with all proceeds reinvested in the Fab Lab",
    "Solar": "5kW",
    "Inverter Size": "4800W",
    "Battery": "5kWh",
    "Storage": "This is a sample storage ipsum",
    "Tariff": "Unlimited tariff",
    "Return": "Unlimited Return",
    "Rating": "AAA",
    "Pilot Goals": [
      "Demonstrate contractual automation and disintermediation of renewable energy project finance using blockchain-based smart contracts, as featured in the OpenSolar platform",
      "Demonstrate alternative finance schemes with pay-to-own models for community ownership of solar assets.",
      "Demonstrate the integration between data from internet-of-things (IoT) devices into payment schemes and climate asset tokenization (Renewable Energy Certificates).",
      "Stress test all features in the OpenSolar platforms, including user experiences, fiat on and offramps and smart contracts.",
      "Provide a blueprint for a finance plan to transform all of Puerto Rico’s public schools into solar powered emergency shelters."
    ],
    "Context": "Two years after hurricane Maria hit the island, schools and local communities are still exposed to a centralized and high-carbon energy system vulnerable to climate impacts. The 2020 Earthquake left ⅓ of the island without power. Cooperatives and schools like FabIDEAS and SU Pasto are ideal places for community owned microgrids to be deployed, in order to provide greater power resilience and usher in a new energy economy to Puerto Rico. Since Hurricane Maria, community cooperatives have become nodal points facilitating discussions of concerned parents on how to increase climate & social resilience in the whole community.\n\nThe Puerto Rican (PR) government and the department of education are working to appoint schools as emergency shelters —nodes with robust energy and communication systems— for the community to reach out in the event of unavoidable climate shocks. Financing is a key gap. This project acts as a pilot finance mechanism that can help bridge the finance gap to make solar powered schools and community centers more affordable.",
    "Opportunity Description": "Cooperativa Fábrica de Ideas de Aibonito (FabIDEAS Coop), is a project that has received the support of Institution Nueva Escuela (INE), an independent 501c3 nonprofit organization dedicated to transforming the public education system in Puerto Rico through the Montessori philosophy and methodology. FabIDEAS Coop, is an initiative of the community linked to the INE public school S.U. Pasto in the rural town of Aibonito. FabIDEAS Coop aims to create an economic model in which a cooperative of Montessori materials with five initial members serves as an economic engine for the production and distribution of educational products and children furniture, where each additional member of the community that joins the production guild can learn product design and gradually increase his/her income source. It will act as a hub for education in distributed manufacturing to the students of SU Pasto and as an emergency shelter for community members. \n\nThe current project entails the installation of a 5kW system with InverSol’s Lumen battery and inverter unit. Solar will power critical loads in the building, including emergency lights, a telecommunication system, and main manufacturing equipment. The installed system is priced at $12’000, with $9000 being donated by Council Rock / InverSol to support the pilot and coop. The Digital Currency Initiative at the MIT Media Lab will provide a grant of $4000 to cover $3000 of labor cost by the inverSol team and $1000 of other installation services.  The FabIDEAS Coop has agreed to match this $4000 by paying for the solar electricity at the standard utility price (which the building is subject to when it purchases power from the grid) until reaches this amount in cumulative solar power payments. Once these funds accrue they will be reinvested in manufacturing units for the Fab Lab. \n\nThe project is the first full pilot of the Open Solar platform and will test the smart contracts and digital currency enabled by the platform to automate all the dynamics behind the $4000 grant, the solar power payments, and the Renewable Energy Certificates generated by the system. Financial transactions will be automated based on the data read by inverSol’s Lumen unit. \n\t\t",
    "Architecture Design Description": "The solar installation will be a behind-the-meter backup setup, to avoid net metering with PREPA’s grid. Future expansion deployments could consider a grid-tied two-way system. The 5kW solar photovoltaics will be installed on the FabIDEAS main building’s roof and connected to the inverSOL’s Lumen unit equipped with a 5kWh battery, a 5kW inverter, a charge regulator and internet-of-things (IoT) functionality.",
    "Installation Archetype": "This will be a model installation in that the solar and battery support a subpanel of the building circuitry, where only critical loads have been connected. Large manufacturing machinery will not be connected to the subpanel. The system will be configured as a grid-tied installation, in that the main grid can also support other loads in the panel as well as be used to power the battery bank. The installation allows for the interconnection of an emergency generator if needed.",
    "IT Infrastructure": "Main power data readings will come directly from the Lumen all-in-one powermeter unit, transmitting secure data via MQTT protocol. A second revenue-grade meter with IoT pre-pay functionality will be added for further testing integrations. IoT readings from the Lumen system will be used in a smart contract oracle to verify & validate readings for payment and REC generation. A whole building non-invasive powermeter is also contemplated to critical vs. general loads.",
    "Highlighted Product": "\n\t\tinverSOL Lumen:\nLumen by inverSOL is a smart renewable energy system for the home providing greater energy independence and backup power. Lithium NMC (LiNMC ) batteries used in Lumen are validated and produced with uncompromised safety and quality control. Wireless connectivity and computing platform allow for remote control through an app, software upgrades and smart energy management features. \n\nThe Lumen smart features minimize wasted solar power and reduce energy bills, eliminating the need for net metering. The proprietary algorithm built in the Lumen brain ensures solar energy is used even when there is no Sun. Enhanced user experience through an interactive touchscreen and remote control through a mobile app allow to track energy usage and savings. New features available with software updates. Robust and sleek design make Lumen a seamless fit for any interior. Touchscreen and Interactive Design ensure enhanced user experience.\n\t\t",
    "CommunityEngagement": {
      "Consultation": "The MIT and Yale team will convene meetings with the FabIDEAS cooperative board to discuss project details and outreach opportunities. The team has already convened a meeting with the Parent-Teacher Organisation of the SU Pasto school, thanks to the coordination of the school’s principal Janice Alejandro, to discuss the role of new finance mechanisms for solar in the local community. Over 50 members of the community gathered to discuss the project, with unanimous approval and significant interest for its replication.",
      "Participation": "The FabIDEAS cooperative community will source volunteers and champions to act as caretakers of the system to monitor its status, report any qualitative information and coordinate with the operation & maintenance required. ",
      "Outreach": "The system will be installed with instructions and visual explanations so that it can act as a pedagogical site for students and community members to learn about the merits of solar energy, electricity and basic electronics. Talks about solar energy will be convened every semester in the context of climate change communication to the community. ",
      "Governance": "The board of the Cooperative and its acting President Maria Pastor will convene bi yearly meeting with the Yale-MIT team (i.e. the originators) to review processes and performance of the solar system and the smart contract."
    },
    "BusinessNumbers": {
      "Description": "The system will be funded by an in-kind donation of inverSOL, providing the solar hardware, and a grant from the Digital Currency Initiative at MIT to cover labor and other service costs. inverSOL’s donation involves the $9000 for 5kW system with  issued by the PR Department of Education covered the principle cost, used for labor and materials. The PPA revenue accrues to pay coupons and mature the bond. The MIT is registered as a first-loss guarantor.",
      "Capital Expenditure": "The expected capital cost of the project is $13000, including the U$S 9000 product value of a 5kW solar array with a Lumen unity (donated by inverSOL), $3000 of labor costs and $1000 for contingency and other services (covered by the DCI grant).",
      "Project Revenue": "The FabIDEAS cooperative will pay for the solar electricity generated at a standard $/kWh local tariff using an Open Solar platform wallet. Once accumulated payments reach $4000 (stored in the project’s smart contract escrow), these will be released back to the FabIDEAS coop wallet to be used for reinvesting in the fab lab. ",
      "Project Expenses": "The project has an O&M (Operation & Management) contingency fund of $1000, but will otherwise will be covered by inverSOL’s guarantee for 5 years. After this period, the cooperative will be responsible for O&M. ",
      "Non-profit": "No net-income or profits will be generated by this project. "
    },
    "Tax": "1000",
    "Daily Average Generation": "20 kWh",
    "Maturity": "2021",
    "Acquisition": "Sample Acquisition",
    "Amount Funded": 0
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/project/get" %}
{% api-method-summary %}
Get Project
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**https://api2.openx.solar/project/get?index=1&username=admin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="index" type="string" required=true %}

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

```text
{
  "Index": 1,
  "TotalValue": 4000,
  "Lock": false,
  "LockPwd": "",
  "Chain": "stellar",
  "OneTimeUnlock": "",
  "AmountOwed": 0,
  "Reputation": 0,
  "Votes": 0,
  "OwnershipShift": 0,
  "StageData": null,
  "StageChecklist": null,
  "InvestorMap": null,
  "SeedInvestorMap": null,
  "WaterfallMap": null,
  "RecipientIndex": -1,
  "OriginatorIndex": -1,
  "GuarantorIndex": -1,
  "ContractorIndex": -1,
  "InvestorIndices": null,
  "SeedInvestorIndices": null,
  "DateInitiated": "",
  "DateFunded": "",
  "DateLastPaid": 0,
  "AuctionType": "",
  "InvestmentType": "munibond",
  "PaybackPeriod": 2419200000000000,
  "Stage": 3,
  "InvestorAssetCode": "",
  "DebtAssetCode": "",
  "PaybackAssetCode": "",
  "SeedAssetCode": "",
  "SeedInvestmentFactor": 0,
  "SeedInvestmentCap": 0,
  "EscrowPubkey": "",
  "EscrowLock": false,
  "MoneyRaised": 0,
  "SeedMoneyRaised": 0,
  "EstimatedAcquisition": 0,
  "BalLeft": 0,
  "AdminFlagged": false,
  "FlaggedBy": 0,
  "UserFlaggedBy": null,
  "Reports": 0,
  "TellerUrl": "",
  "BrokerUrl": "mqtt.openx.solar",
  "TellerPublishTopic": "opensolartest",
  "Metadata": "Aibonito Pilot Project",
  "Name": "5kW Solar at FabIDEAS Coop - Pilot 1",
  "City": "Aibonito",
  "State": "Puerto Rico",
  "Country": "USA",
  "Panel Size": "50 x 100W",
  "Image": "",
  "Interest Rate": 0,
  "Investment Cap": 0,
  "Amount Self Funded": 0,
  "Main Developer Index": 0,
  "Developer Indices": null,
  "Contractor Fee": 0,
  "Originator Fee": 0,
  "Developer Fee": null,
  "Location": "Puerto Rico",
  "Donation Type": "Grant",
  "Originator": "Martin Wainstein",
  "Description": "5kW solar to be owned by the FabIDEAS Community Cooperative in Aibonito. The Coop is part of the Institution Nueva Escuela (INE), and will host a Fab Lab manufacturing montessori school supplies.",
  "Bullet1": "Powering a unique social entrepreneurship model through a local cooperative",
  "Bullet2": "Power purchase agreement tied to the standard local Aibonito tariff",
  "Bullet3": "Pay-to-own solar model for the coop with all proceeds reinvested in the Fab Lab",
  "Solar": "5kW",
  "Inverter Size": "4800W",
  "Battery": "5kWh",
  "Storage": "This is a sample storage ipsum",
  "Tariff": "Unlimited tariff",
  "Return": "Unlimited Return",
  "Rating": "AAA",
  "Pilot Goals": [
    "Demonstrate contractual automation and disintermediation of renewable energy project finance using blockchain-based smart contracts, as featured in the OpenSolar platform",
    "Demonstrate alternative finance schemes with pay-to-own models for community ownership of solar assets.",
    "Demonstrate the integration between data from internet-of-things (IoT) devices into payment schemes and climate asset tokenization (Renewable Energy Certificates).",
    "Stress test all features in the OpenSolar platforms, including user experiences, fiat on and offramps and smart contracts.",
    "Provide a blueprint for a finance plan to transform all of Puerto Rico’s public schools into solar powered emergency shelters."
  ],
  "Context": "Two years after hurricane Maria hit the island, schools and local communities are still exposed to a centralized and high-carbon energy system vulnerable to climate impacts. The 2020 Earthquake left ⅓ of the island without power. Cooperatives and schools like FabIDEAS and SU Pasto are ideal places for community owned microgrids to be deployed, in order to provide greater power resilience and usher in a new energy economy to Puerto Rico. Since Hurricane Maria, community cooperatives have become nodal points facilitating discussions of concerned parents on how to increase climate & social resilience in the whole community.\n\nThe Puerto Rican (PR) government and the department of education are working to appoint schools as emergency shelters —nodes with robust energy and communication systems— for the community to reach out in the event of unavoidable climate shocks. Financing is a key gap. This project acts as a pilot finance mechanism that can help bridge the finance gap to make solar powered schools and community centers more affordable.",
  "Opportunity Description": "Cooperativa Fábrica de Ideas de Aibonito (FabIDEAS Coop), is a project that has received the support of Institution Nueva Escuela (INE), an independent 501c3 nonprofit organization dedicated to transforming the public education system in Puerto Rico through the Montessori philosophy and methodology. FabIDEAS Coop, is an initiative of the community linked to the INE public school S.U. Pasto in the rural town of Aibonito. FabIDEAS Coop aims to create an economic model in which a cooperative of Montessori materials with five initial members serves as an economic engine for the production and distribution of educational products and children furniture, where each additional member of the community that joins the production guild can learn product design and gradually increase his/her income source. It will act as a hub for education in distributed manufacturing to the students of SU Pasto and as an emergency shelter for community members. \n\nThe current project entails the installation of a 5kW system with InverSol’s Lumen battery and inverter unit. Solar will power critical loads in the building, including emergency lights, a telecommunication system, and main manufacturing equipment. The installed system is priced at $12’000, with $9000 being donated by Council Rock / InverSol to support the pilot and coop. The Digital Currency Initiative at the MIT Media Lab will provide a grant of $4000 to cover $3000 of labor cost by the inverSol team and $1000 of other installation services.  The FabIDEAS Coop has agreed to match this $4000 by paying for the solar electricity at the standard utility price (which the building is subject to when it purchases power from the grid) until reaches this amount in cumulative solar power payments. Once these funds accrue they will be reinvested in manufacturing units for the Fab Lab. \n\nThe project is the first full pilot of the Open Solar platform and will test the smart contracts and digital currency enabled by the platform to automate all the dynamics behind the $4000 grant, the solar power payments, and the Renewable Energy Certificates generated by the system. Financial transactions will be automated based on the data read by inverSol’s Lumen unit. \n\t\t",
  "Architecture Design Description": "The solar installation will be a behind-the-meter backup setup, to avoid net metering with PREPA’s grid. Future expansion deployments could consider a grid-tied two-way system. The 5kW solar photovoltaics will be installed on the FabIDEAS main building’s roof and connected to the inverSOL’s Lumen unit equipped with a 5kWh battery, a 5kW inverter, a charge regulator and internet-of-things (IoT) functionality.",
  "Installation Archetype": "This will be a model installation in that the solar and battery support a subpanel of the building circuitry, where only critical loads have been connected. Large manufacturing machinery will not be connected to the subpanel. The system will be configured as a grid-tied installation, in that the main grid can also support other loads in the panel as well as be used to power the battery bank. The installation allows for the interconnection of an emergency generator if needed.",
  "IT Infrastructure": "Main power data readings will come directly from the Lumen all-in-one powermeter unit, transmitting secure data via MQTT protocol. A second revenue-grade meter with IoT pre-pay functionality will be added for further testing integrations. IoT readings from the Lumen system will be used in a smart contract oracle to verify & validate readings for payment and REC generation. A whole building non-invasive powermeter is also contemplated to critical vs. general loads.",
  "Highlighted Product": "\n\t\tinverSOL Lumen:\nLumen by inverSOL is a smart renewable energy system for the home providing greater energy independence and backup power. Lithium NMC (LiNMC ) batteries used in Lumen are validated and produced with uncompromised safety and quality control. Wireless connectivity and computing platform allow for remote control through an app, software upgrades and smart energy management features. \n\nThe Lumen smart features minimize wasted solar power and reduce energy bills, eliminating the need for net metering. The proprietary algorithm built in the Lumen brain ensures solar energy is used even when there is no Sun. Enhanced user experience through an interactive touchscreen and remote control through a mobile app allow to track energy usage and savings. New features available with software updates. Robust and sleek design make Lumen a seamless fit for any interior. Touchscreen and Interactive Design ensure enhanced user experience.\n\t\t",
  "CommunityEngagement": {
    "Consultation": "The MIT and Yale team will convene meetings with the FabIDEAS cooperative board to discuss project details and outreach opportunities. The team has already convened a meeting with the Parent-Teacher Organisation of the SU Pasto school, thanks to the coordination of the school’s principal Janice Alejandro, to discuss the role of new finance mechanisms for solar in the local community. Over 50 members of the community gathered to discuss the project, with unanimous approval and significant interest for its replication.",
    "Participation": "The FabIDEAS cooperative community will source volunteers and champions to act as caretakers of the system to monitor its status, report any qualitative information and coordinate with the operation & maintenance required. ",
    "Outreach": "The system will be installed with instructions and visual explanations so that it can act as a pedagogical site for students and community members to learn about the merits of solar energy, electricity and basic electronics. Talks about solar energy will be convened every semester in the context of climate change communication to the community. ",
    "Governance": "The board of the Cooperative and its acting President Maria Pastor will convene bi yearly meeting with the Yale-MIT team (i.e. the originators) to review processes and performance of the solar system and the smart contract."
  },
  "BusinessNumbers": {
    "Description": "The system will be funded by an in-kind donation of inverSOL, providing the solar hardware, and a grant from the Digital Currency Initiative at MIT to cover labor and other service costs. inverSOL’s donation involves the $9000 for 5kW system with  issued by the PR Department of Education covered the principle cost, used for labor and materials. The PPA revenue accrues to pay coupons and mature the bond. The MIT is registered as a first-loss guarantor.",
    "Capital Expenditure": "The expected capital cost of the project is $13000, including the U$S 9000 product value of a 5kW solar array with a Lumen unity (donated by inverSOL), $3000 of labor costs and $1000 for contingency and other services (covered by the DCI grant).",
    "Project Revenue": "The FabIDEAS cooperative will pay for the solar electricity generated at a standard $/kWh local tariff using an Open Solar platform wallet. Once accumulated payments reach $4000 (stored in the project’s smart contract escrow), these will be released back to the FabIDEAS coop wallet to be used for reinvesting in the fab lab. ",
    "Project Expenses": "The project has an O&M (Operation & Management) contingency fund of $1000, but will otherwise will be covered by inverSOL’s guarantee for 5 years. After this period, the cooperative will be responsible for O&M. ",
    "Non-profit": "No net-income or profits will be generated by this project. "
  },
  "Tax": "1000",
  "Daily Average Generation": "20 kWh",
  "Maturity": "2021",
  "Acquisition": "Sample Acquisition",
  "Amount Funded": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/projects" %}
{% api-method-summary %}
Get Projects at stage
{% endapi-method-summary %}

{% api-method-description %}
**curl -X GET "**https://api2.openx.solar/projects?stage=3&username=admin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft**"**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="stage" type="string" required=true %}

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

```text
[
  {
    "Index": 1,
    "TotalValue": 4000,
    "Lock": false,
    "LockPwd": "",
    "Chain": "stellar",
    "OneTimeUnlock": "",
    "AmountOwed": 0,
    "Reputation": 0,
    "Votes": 0,
    "OwnershipShift": 0,
    "StageData": null,
    "StageChecklist": null,
    "InvestorMap": null,
    "SeedInvestorMap": null,
    "WaterfallMap": null,
    "RecipientIndex": -1,
    "OriginatorIndex": -1,
    "GuarantorIndex": -1,
    "ContractorIndex": -1,
    "InvestorIndices": null,
    "SeedInvestorIndices": null,
    "DateInitiated": "",
    "DateFunded": "",
    "DateLastPaid": 0,
    "AuctionType": "",
    "InvestmentType": "munibond",
    "PaybackPeriod": 2419200000000000,
    "Stage": 3,
    "InvestorAssetCode": "",
    "DebtAssetCode": "",
    "PaybackAssetCode": "",
    "SeedAssetCode": "",
    "SeedInvestmentFactor": 0,
    "SeedInvestmentCap": 0,
    "EscrowPubkey": "",
    "EscrowLock": false,
    "MoneyRaised": 0,
    "SeedMoneyRaised": 0,
    "EstimatedAcquisition": 0,
    "BalLeft": 0,
    "AdminFlagged": false,
    "FlaggedBy": 0,
    "UserFlaggedBy": null,
    "Reports": 0,
    "TellerUrl": "",
    "BrokerUrl": "mqtt.openx.solar",
    "TellerPublishTopic": "opensolartest",
    "Metadata": "Aibonito Pilot Project",
    "Name": "5kW Solar at FabIDEAS Coop - Pilot 1",
    "City": "Aibonito",
    "State": "Puerto Rico",
    "Country": "USA",
    "Panel Size": "50 x 100W",
    "Image": "",
    "Interest Rate": 0,
    "Investment Cap": 0,
    "Amount Self Funded": 0,
    "Main Developer Index": 0,
    "Developer Indices": null,
    "Contractor Fee": 0,
    "Originator Fee": 0,
    "Developer Fee": null,
    "Location": "Puerto Rico",
    "Donation Type": "Grant",
    "Originator": "Martin Wainstein",
    "Description": "5kW solar to be owned by the FabIDEAS Community Cooperative in Aibonito. The Coop is part of the Institution Nueva Escuela (INE), and will host a Fab Lab manufacturing montessori school supplies.",
    "Bullet1": "Powering a unique social entrepreneurship model through a local cooperative",
    "Bullet2": "Power purchase agreement tied to the standard local Aibonito tariff",
    "Bullet3": "Pay-to-own solar model for the coop with all proceeds reinvested in the Fab Lab",
    "Solar": "5kW",
    "Inverter Size": "4800W",
    "Battery": "5kWh",
    "Storage": "This is a sample storage ipsum",
    "Tariff": "Unlimited tariff",
    "Return": "Unlimited Return",
    "Rating": "AAA",
    "Pilot Goals": [
      "Demonstrate contractual automation and disintermediation of renewable energy project finance using blockchain-based smart contracts, as featured in the OpenSolar platform",
      "Demonstrate alternative finance schemes with pay-to-own models for community ownership of solar assets.",
      "Demonstrate the integration between data from internet-of-things (IoT) devices into payment schemes and climate asset tokenization (Renewable Energy Certificates).",
      "Stress test all features in the OpenSolar platforms, including user experiences, fiat on and offramps and smart contracts.",
      "Provide a blueprint for a finance plan to transform all of Puerto Rico’s public schools into solar powered emergency shelters."
    ],
    "Context": "Two years after hurricane Maria hit the island, schools and local communities are still exposed to a centralized and high-carbon energy system vulnerable to climate impacts. The 2020 Earthquake left ⅓ of the island without power. Cooperatives and schools like FabIDEAS and SU Pasto are ideal places for community owned microgrids to be deployed, in order to provide greater power resilience and usher in a new energy economy to Puerto Rico. Since Hurricane Maria, community cooperatives have become nodal points facilitating discussions of concerned parents on how to increase climate & social resilience in the whole community.\n\nThe Puerto Rican (PR) government and the department of education are working to appoint schools as emergency shelters —nodes with robust energy and communication systems— for the community to reach out in the event of unavoidable climate shocks. Financing is a key gap. This project acts as a pilot finance mechanism that can help bridge the finance gap to make solar powered schools and community centers more affordable.",
    "Opportunity Description": "Cooperativa Fábrica de Ideas de Aibonito (FabIDEAS Coop), is a project that has received the support of Institution Nueva Escuela (INE), an independent 501c3 nonprofit organization dedicated to transforming the public education system in Puerto Rico through the Montessori philosophy and methodology. FabIDEAS Coop, is an initiative of the community linked to the INE public school S.U. Pasto in the rural town of Aibonito. FabIDEAS Coop aims to create an economic model in which a cooperative of Montessori materials with five initial members serves as an economic engine for the production and distribution of educational products and children furniture, where each additional member of the community that joins the production guild can learn product design and gradually increase his/her income source. It will act as a hub for education in distributed manufacturing to the students of SU Pasto and as an emergency shelter for community members. \n\nThe current project entails the installation of a 5kW system with InverSol’s Lumen battery and inverter unit. Solar will power critical loads in the building, including emergency lights, a telecommunication system, and main manufacturing equipment. The installed system is priced at $12’000, with $9000 being donated by Council Rock / InverSol to support the pilot and coop. The Digital Currency Initiative at the MIT Media Lab will provide a grant of $4000 to cover $3000 of labor cost by the inverSol team and $1000 of other installation services.  The FabIDEAS Coop has agreed to match this $4000 by paying for the solar electricity at the standard utility price (which the building is subject to when it purchases power from the grid) until reaches this amount in cumulative solar power payments. Once these funds accrue they will be reinvested in manufacturing units for the Fab Lab. \n\nThe project is the first full pilot of the Open Solar platform and will test the smart contracts and digital currency enabled by the platform to automate all the dynamics behind the $4000 grant, the solar power payments, and the Renewable Energy Certificates generated by the system. Financial transactions will be automated based on the data read by inverSol’s Lumen unit. \n\t\t",
    "Architecture Design Description": "The solar installation will be a behind-the-meter backup setup, to avoid net metering with PREPA’s grid. Future expansion deployments could consider a grid-tied two-way system. The 5kW solar photovoltaics will be installed on the FabIDEAS main building’s roof and connected to the inverSOL’s Lumen unit equipped with a 5kWh battery, a 5kW inverter, a charge regulator and internet-of-things (IoT) functionality.",
    "Installation Archetype": "This will be a model installation in that the solar and battery support a subpanel of the building circuitry, where only critical loads have been connected. Large manufacturing machinery will not be connected to the subpanel. The system will be configured as a grid-tied installation, in that the main grid can also support other loads in the panel as well as be used to power the battery bank. The installation allows for the interconnection of an emergency generator if needed.",
    "IT Infrastructure": "Main power data readings will come directly from the Lumen all-in-one powermeter unit, transmitting secure data via MQTT protocol. A second revenue-grade meter with IoT pre-pay functionality will be added for further testing integrations. IoT readings from the Lumen system will be used in a smart contract oracle to verify & validate readings for payment and REC generation. A whole building non-invasive powermeter is also contemplated to critical vs. general loads.",
    "Highlighted Product": "\n\t\tinverSOL Lumen:\nLumen by inverSOL is a smart renewable energy system for the home providing greater energy independence and backup power. Lithium NMC (LiNMC ) batteries used in Lumen are validated and produced with uncompromised safety and quality control. Wireless connectivity and computing platform allow for remote control through an app, software upgrades and smart energy management features. \n\nThe Lumen smart features minimize wasted solar power and reduce energy bills, eliminating the need for net metering. The proprietary algorithm built in the Lumen brain ensures solar energy is used even when there is no Sun. Enhanced user experience through an interactive touchscreen and remote control through a mobile app allow to track energy usage and savings. New features available with software updates. Robust and sleek design make Lumen a seamless fit for any interior. Touchscreen and Interactive Design ensure enhanced user experience.\n\t\t",
    "CommunityEngagement": {
      "Consultation": "The MIT and Yale team will convene meetings with the FabIDEAS cooperative board to discuss project details and outreach opportunities. The team has already convened a meeting with the Parent-Teacher Organisation of the SU Pasto school, thanks to the coordination of the school’s principal Janice Alejandro, to discuss the role of new finance mechanisms for solar in the local community. Over 50 members of the community gathered to discuss the project, with unanimous approval and significant interest for its replication.",
      "Participation": "The FabIDEAS cooperative community will source volunteers and champions to act as caretakers of the system to monitor its status, report any qualitative information and coordinate with the operation & maintenance required. ",
      "Outreach": "The system will be installed with instructions and visual explanations so that it can act as a pedagogical site for students and community members to learn about the merits of solar energy, electricity and basic electronics. Talks about solar energy will be convened every semester in the context of climate change communication to the community. ",
      "Governance": "The board of the Cooperative and its acting President Maria Pastor will convene bi yearly meeting with the Yale-MIT team (i.e. the originators) to review processes and performance of the solar system and the smart contract."
    },
    "BusinessNumbers": {
      "Description": "The system will be funded by an in-kind donation of inverSOL, providing the solar hardware, and a grant from the Digital Currency Initiative at MIT to cover labor and other service costs. inverSOL’s donation involves the $9000 for 5kW system with  issued by the PR Department of Education covered the principle cost, used for labor and materials. The PPA revenue accrues to pay coupons and mature the bond. The MIT is registered as a first-loss guarantor.",
      "Capital Expenditure": "The expected capital cost of the project is $13000, including the U$S 9000 product value of a 5kW solar array with a Lumen unity (donated by inverSOL), $3000 of labor costs and $1000 for contingency and other services (covered by the DCI grant).",
      "Project Revenue": "The FabIDEAS cooperative will pay for the solar electricity generated at a standard $/kWh local tariff using an Open Solar platform wallet. Once accumulated payments reach $4000 (stored in the project’s smart contract escrow), these will be released back to the FabIDEAS coop wallet to be used for reinvesting in the fab lab. ",
      "Project Expenses": "The project has an O&M (Operation & Management) contingency fund of $1000, but will otherwise will be covered by inverSOL’s guarantee for 5 years. After this period, the cooperative will be responsible for O&M. ",
      "Non-profit": "No net-income or profits will be generated by this project. "
    },
    "Tax": "1000",
    "Daily Average Generation": "20 kWh",
    "Maturity": "2021",
    "Acquisition": "Sample Acquisition",
    "Amount Funded": 0
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/utils/addhash" %}
{% api-method-summary %}
Add Hash
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="choicestr" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="choice" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="projIndex" type="string" required=true %}

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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/tellershutdown" %}
{% api-method-summary %}
Send Teller shutdown email
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="tx2" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="tx1" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="deviceId" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="projIndex" type="string" required=true %}

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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/tellerpayback" %}
{% api-method-summary %}
Send Teller Payback Email
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="projIndex" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="deviceId" type="string" required=true %}

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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/project/get/dashboard" %}
{% api-method-summary %}
Get Project Dashboard
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="index" type="number" required=true %}

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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

