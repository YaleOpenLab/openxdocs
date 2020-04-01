# Architecture

### Introduction

Opensolar is a platform built using the Stellar blockchain that enables investments in solar infrastructure. Opensolar is built on top of openx, a broader "platform of platforms" architecture. Opensolar's initial pilots are targeted at Puerto Rico, a territory that has been frequently subject to hurricanes, earthquakes and more, preventing access to energy for prolonged periods of time. Opensolar aims to automate the entire process of energy production, billing, and asset ownership for the recipient and the process of returns for the investor.

This is done by monitoring energy production using IoT devices, storing the data on a distributed database, and paying for energy consumption over a pre-defined period \(two weeks / a month\) by fetching energy prices from an oracle. The entire workflow is implemented as a series of contracts designed to be run on a hosting service.

### Solar Infrastructure

The solar infrastructure for Opensolar is composed of multiple parts - Solar Panels, IoT devices which report energy generated to an IoT Hub, and an IoT Hub which records the amount of energy generated during every interval of time defined. Opensolar interfaces with the IoT Hub to collect data on energy consumption and the IoT Hub triggers the conditions defined by the smart contract. ****This is done by running a piece of software called the **Teller** on the IoT Hub.

**Teller**

The teller is an executable that interfaces with the platform to constantly report progress, store energy data on the blockchain, and trigger payments every payment interval. The teller contains information about the recipient and draws funds from the recipient's account to pay back towards the smart contract. The teller also acts as a mini CLI emulator and can be used to query limited information like the amount of money left in the recipient's account and the latest state of the teller from the teller.

**MQTT Broker**

The IoT devices that are linked to the solar panels transmit data using the MQTT protocol. The MQTT protocol requires a transmitter \(in this case the IoT devices linked to the solar panel\), a broker to broadcast the messages received from the transmitter, and a receiver which can connect to the broker and subscribe to messages from the transmitter. The broker can either be run alongside the platform or can be run on the IoT Hub, depending on the energy specifications of the IoT Hub and its capabilities. Opensolar runs an MQTT broker at mqtt.openx.solar which acts as the broker for projects on the opensolar platform.

**Swytch.io**

Swytch.io is a third party provider which generates Renewable Energy Certificates \(RECs\) for each Megawatt of energy generated. A copy of the data sent to mqtt.openx.solar is also sent to Swytch.io to mint RECs. These RECs can be sold by the recipient or investor on secondary markets as defined in the investment contract. Swytch also provides an interactive dashboard where recipients can visualize the amount of energy generated throughout the day and other statistics in graph form.

### Smart Contracts

Opensolar is powered by a collection of smart contracts split across modular parts. The primary contract housed in `contract.go` combines functionality from multiple parts.

### KYC

AnchorUSD requires KYC to be done through its portal. TODO

### Investors

Investors are the primary entities on the opensolar platform. They invest in projects, and get returns from receivers.

### Recipients \(Receivers\)

Receivers of a project are the end-beneficiaries of a project. They are usually school co-op societies, agricultural co-ops, and so on. They are responsible for

1. Creating a project with the help of Originators
2. Receiving quotes for a project with the help of Contractors
3. Installing the project with the help of Developers, and
4. Paying back the Investors for their investment in the project.

A recipient may be single person or a company in charge of a specific society.

### Guarantors

Guarantors provide guarantee to investors against receivers who might default on payments. Guarantors are the equivalent of insurance firms.

### Contractors

Contractors are entities that bid for the right to install projects on behalf of the recipient. They can perform the role of a developer as well.

### Developers

Developers are entities that install the technical requirements of the project. Developers are involved in project installation after contractors.

### Originators

Originators are entities that propose projects capable of receiving investment to recipients.

### Project Stages

An opensolar project is divided into 9 stages ordered chronologically:

Stage 1: **Engagement**  
Stage 2: **Quotes**  
Stage 3: **Signing**  
Stage 4: **Investment**  
Stage 5: **Construction**  
Stage 6: **Interconnection**  
Stage 7: **Legacy**  
Stage 8: **Handoff**  
Stage 9: **End of Life**

Each stage transition is regulated by the smart contract.

### Investment Models

Opensolar aims to support multiple investment models but right now, only one kind of investment \(munibond\) is supported. Others can be added as modular packages and imported into the parent smart contract when required.

### Platform Infrastructure

The opensolar platform and the openx platform of platforms are hosted on separate AWS instances. They communicate with each other through the platform-platform API defined by openx. The platform communicates with the blockchain, MQTT broker, IPFS and other parts  required for opensolar to work as expected.

### Stablecoin

Opensolar makes use of USDx, a digital representation of the US Dollar on Stellar provided by AnchorUSD. Procuring USDx requires one to undergo Know Your Customer \(KYC\) checks done by AnchorUSD. Once a user completes the checks required by AnchorUSD, they can invest in any project on the opensolar platform.

USDx can also be procured on the Stellar DEX and used to invest on the platform.

Recipients can purchase USDx through AnchorUSD's website, and are required to go through the same KYC process as required of investors. Once a recipient loads funds into their account and when there is sufficient balance to pay towards the bills generated, the smart contract triggers payments. If there is insufficient balance, the platform sends a reminder to the recipient to load funds into their account.

