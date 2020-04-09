---
description: A doc describing what the teller is and its functions
---

# Teller

Opensolar uses a piece of software called the "Teller" as an interface between the platform and the installed solar energy grid on site. The teller accumulates data received from the solar energy grid, calculates the net amount of energy every week and communicates that to the platform. The amount to be paid each month is then calculated from the energy generated, as  
  
`Amount Owed ($) = Energy Generated in 1 month (kWh) * Price per kWh ($/Kwh)`

The price for energy per kWH is derived from standard government sources and served to Opensolar via an oracle. For the pilot platform, this price is fixed at $0.20/kWh.

The teller performs auxiliary functions that are required to prove ownership and correct accumulation of data. It tracks the device's location, stores the solar grid's state on IPFS every week, stores the associated IPFS hash on the blockchain at regular intervals, and provides functions for a receiver to view the balance and other data associated with a project. These functions can be accessed through the teller's Command line interface.

The teller requires two things apart from the source to start:

1. A config file: The teller needs a config file in order to be able to work correctly. This config file is based on the `dummyconfig.yaml` file and contains details of the recipient, their password, mqtt credentials, etc.
2. An SSL certificate file \(self signed / third party signed\): This is required in order for the teller to be able to listen on port 443 and serve pieces of data when required/

On first initialisation, the teller generates and commnunicates a unique device id to the platform along with its location, so the device can be tracked to see if its running properly. 

All communication beween the teller and the platform occurs through JSON-RPC APIs.

