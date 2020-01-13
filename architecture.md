---
description: A thorough description of the openx/opensolar architecture
---

# Architecture

Intro: Openx is a "platform of platforms" architecture for enabling investments using blockchains. Openx is built on top of the Stellar blockchain but is designed to be blockchain agnostic and can support multiple blockchain platforms in parallel.

Openx provides a basic set of features for platforms that build on top of it:

* Users
  * Primary and Secondary Stellar Wallets
  * Basic support for Algorand Wallets
* Platforms
* Stablecoins
* KYC \(w/o identity verification\) suport using ComplyAdvantage
* Configurable CI support using a build server

The [create-openx-app](https://github.com/YaleOpenLab/create-openx-app) application provides this functionality out of the box and can be used to bootstrap platforms that wish to build on top of Stellar.

Openx is designed to work using JSON-RPC APIs. Each of the above mentioned functionality uses them and CLI tools like the [emulator](https://github.com/Varunram/openx-cli) use the RPCs to interact with openx without the frontend application.

Openx does not have a frontend designed for it but such a design would be similar to opensolar's frontend, which will be described in detail below.

