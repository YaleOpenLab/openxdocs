# Architecture

### Introduction

Opensolar is a platform built on top of openx and the Stellar blockchain that enables investments in solar infrastructure. Opensolar's initial pilots are targeted at Puerto Rico, a territory that has been ferquently subject to hurricanes, earthquakes and more, preventing access to energy for prolonged period of time. Opensolar aims to automate the entire process of energy production, billing and asset ownership for the recipient and the process of returns for the investor. This is done by monitoring energy production using IoT devices, storing the data on a distributed database, and paying for energy consumption over a pre-defined period \(two weeks / a month\) by fetchin g energy prices from an oracle. The entire workflow is implemented as a series of contracts designed to be run on the platform instance.

### Solar Infrastructure

Solar Infrastructure is composed of multiple parts - Solar Panels, IoT devices which report energy generated to an IoT Hub, and an IoT Hub which records the amount of energy generated during every interval of time defined. Opensolar interfaces with the IoT Hub to collect data on energy consumption and trigger the conditions defined by the smart contract. ****This is done by running an executable called the **Teller** on the IoT Hub.

**Teller**

The teller is an executable that interfaces with the opensolar platform to constantly report progress, stores energy data on the blockchain, and automatically triggers payments every payment interval. The teller contains information about the recipient so it can draw funds from the recipient's account for paying back towards the invesment contract. The teller also acts as a mini CLI emulator which can be used to query limited things like the amount of money left in the recipient's account and the latest state of the teller.

**MQTT Broker**

The IoT devices that are linked to the solar panels transmit data using the MQTT protocol. The MQTT protocol requires a transmitter \(in this case the IoT devices linked to the solar panel\), a broker to broadcast the messages received from the transmitter, and a receiver which can connect to the broker and subscribe to messages from the transmitter. The broker can either be run alongside the platform or can be run on the IoT Hub, depending on the energy specifications of the IoT Hub and its capabilities. Opensolar runs an MQTT broker at mqtt.openx.solar which acts as the broker for projects on the opensolar platform.

### Platform Infrastructure

The opensolar platform and the openx instance associated with it are hosted on separate AWS instances. They communicate with each oteher through the platform-platform API defined by openx. The platform communicates with the broker, IPFS and other parts that are required in order for opensolar to work as expected.

