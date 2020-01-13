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

### Stellar

Stellar is a blockchain focused on layer 1 global payments. Stellar provides a limited set of functonality that can be used to emulate various actors in the global financial space. Stellar follows an account based system similar to Ethereum. The list of operations that we use in openx/opensolar along with its use are listed below:

* **Create Account**: To create user accounts on the platform
* **Payment**: To move money between different accounts
* **Buy Offer**: To exchange XLM and other currencies on the Stellar DEX \(buy\)
* **Sell Offer**: To exchange XLM and other currencies on the Stellar DEX \(sell\)
* **Set Options**: Multisig, Escrow accounts
* **Change Trust**: Multisig, Escrow accounts

Stellar's blockchain client broadly has two parts:

* [Stellar-core](https://github.com/stellar/stellar-core): Stellar core is the blockchain client that communicates with other nodes on the platform and takes part in the Stellar consensus algorithm
* [Horizon](https://godoc.org/github.com/stellar/go/clients/horizon): Horizon is the API instance that communicates with the Stellar core platform and can be used to query the status of the blockchain.

Openx right now connects to the Stellar Development Foundation's Horizon nodes by default, although a platform can choose to run its own node and connect to it. This however, would not provide much additional censorship resistance since the [quorum that Stellar depends on consensus mostly rely on the Stellar Foundation's nodes.](https://godoc.org/github.com/stellar/go/clients/horizon)

Stellar has a set of advantages and disadvantages associated with it, and we decided to experiment to evaluate the positives and negatives of using it for openx/solar.

#### Advantages:

* **The Stellar SDK** is easy to use, moderately documented, making it easy to use it to interact with the blockchain. The current backend makes extensive use of the API in order to perform operations on transactions, accounts and similar. The Stellar Go SDK is also under active maintenance and it makes it easy to write security critical applications.
* **Horizon API**
* Having **easy P2P assets** allows the exploration of more functionality at little added cost.
* **Easy primitive modelling**: Stellar makes it easy to construct primitives like escrow accounts, multisig, variable signer weight and more. This allows us to write bug free constructs without worrying about the security of the underlying contracts.

**Disadvantages**

* **Small developer and user ecosystem**: The Stellar ecosystem kickstarted in 2014 has a limited developer / partner ecosystem. As a result, finding partners who have similar goals as the platform \(eg. for providing onboarding services\) is difficult
* **The lack of onboarding infrastructure**: Stellar's on and off ramp presence is restricted to two startups, [_AnchorUSD_](https://www.anchorusd.com) and [_StrongholdUSD_](https://stronghold.co). AnchorUSD is a startup out of YCombinator and supported by grants from the Stellar foundation, and Stronghold is a company funded by IBM. StrongholdUSD charges $10000/mo and AnchorUSD does not charge anything for using their services currently. AnchorUSD's APIs and infrastructure are limited, making UI and UX integrations with the frontend difficult. Alternatives to the above companies do not seem to exist nor do they seem to be in the works to gravitate towards.
* **Lack of liquidity and absence of major infrastructure**: AnchorUSD is not listed on exchanges and liquidity for the USD/XLM pair on the Stellar DEX is low. The overall lack of infrastructure for buying XLM is a broader concern since only BTC/ETH/XRP seem to have readily usable onramps.
* **Lack of developer support infrastructure**: When developing a platform, it is critical to be able to connect with other people working on similar platforms.
* **Limited functionality**: Stellar has a limited set of functions, even smaller than Bitcoin. This makes designing complex primitives difficult.
* **Security issues**: The Stellar blockchain halted for about 4 hours in May 2019 and was attributed to a crash in the SDF's nodes. Given a majority of the network uses default quorums which trust SDF nodes, this presents a problem for censorship resistance.

