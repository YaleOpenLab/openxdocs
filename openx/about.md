---
description: A description of the openx/opensolar interaction and architecture
---

# About

#### Introduction

Openx's \(and Opensolar's\) architecture is not dependent upon any single blockchain. It is designed to be used with any blockchain as long as there is a contract to interact with a blockchain. Openx right now supports only Stellar but adding support for new blockchains is easy, only requiring the addition of handlers that communicate with other openx fragments. A platform based on Openx has the following parts:

1. A Smart Contract that performs the core functions of the platform 
2. A JSON-RPC interface through which the frontend and other pieces of software can interact with the backend.
3. Auxiliary packages that handle functions like KYC, Stablecoins, different Investment models, etc

The functionality associated with each package within the platform is exposed through a JSON-RPC API. This API follows a token based authentication scheme which callers can invoke.

Openx provides a base set of JSON-RPC endpoints, a user structure for different users on the platform, optional Know Your Customer \(KYC\) functionality, and other features that are useful for constructing a skeletal platform. Openx platform skeletons can be easily created using the CLI based tool create-openx-app, or can be forked from the main opensolar repository.

There is one entity on the openx platform that acts as a parent entity for all entities on other platforms - the "User" entity. This entity contains fields that are required for maintaining cross-compatibility with other openx based platforms. It also contains handlers for all cryptocurrencies supported by openx, and platforms are highly recommended to import this functionality from openx. The entity also contains other pieces relevant for a user such as KYC registration and stablecoin support.

As a rule, cryptocurrency operations and handling must take place within the parent openx platform. If platforms would like to add support for other cryptocurrencies, such functionality must be added to the openx repository to enable cross openx platform investments.

Openx uses boltDB, a key value pair database for its internal storage, in order to store user credentials, encrypted user seed, and more.

Openx provides a set of features for platforms that build on top of it:

* Users
  * Primary and Secondary Stellar Wallets
  * Basic support for Algorand Wallets
* Platforms
* Stablecoins
* KYC \(w/o identity verification\) suport using ComplyAdvantage
* Configurable CI support using a build server

The [create-openx-app](https://github.com/YaleOpenLab/create-openx-app) application provides this functionality out of the box and can be used to bootstrap platforms that wish to build on top of Stellar.

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

### Users

Users can take multiple roles in an openx-powered platform:

* Investors
* Recipents
* Developers
* Contractors
* Originators
* Guarantors

and more. Openx leaves the requirements for these roles to the builders of the platform but defines a base layer user structure that can be used by any platform. This structure contains details like 

* Name
* Description
* Address
* Email
* Stellar and Algorand Wallets
* Local Assets

and more. For platforms that want to perform AML/KYC screening, we provide API integration with [ComplyAdvantage](https://complyadvantage.com/) \(does not provide identity verification\).

Users can be of two types:

* **Individual accounts:** Individual aaccounts are held and represented by one individual.
* **Company accounts:** Company accounts are held by one individual but represent a company. KYC for a company differs from that of an individual.

More types can be defined in the future as required \(and platforms can defined more types if they should so require\)

### Platforms

Platforms in openx refer to platforms that build on top of openx that enable investments in a specific asset class. Opensolar is an example of a platform \(which enables investments in solar energy projects\). Platforms are separate entities in Openx, and do not affect the base openx platform in any way. Users that have an openx account can simultaneously invest in multiple platforms. Users on a platform can choose to be any entity as defined by the constructs of the platform. These roles are not reflected on openx.

Platforms do not handle wallets and similar infrastructure. All wallet related code is handled by openx to provide safety and security. The smart contracts that power the platform can use the different functionalities offered by openx to do various functions. Platforms are not allowed to write their own wallet handling logic since they may create new bugs, making auditing difficult.

Platforms need to be registered on openx and should obtain a unique code that enables them to user the platform-platform API. The API grants access to a privileged set of functions and allows other platforms to create new users, retrieve users, get openx constants and more.

### Administrators

Openx has support for platform administrators who can perform different functions like

* Seeing all users on the platform
* Manually enabling KYC for a user
* Banning a user
* Sending emails to users
* FUTURE: manually triggering smart contracts

Admins are trusted entities who ideally should be the same as those running the platform on the cloud instance. Admins however, do not have access to any user account and can not perform functions like resetting passwords or investing in projects.

### Stablecoins

Stablecoins are digital representations of fiat currencies. Common examples are Tether, USDCoin and more. Stablecoins are usually based off Bitcoin or Ethereum but since openx builds on top of Stellar, it uses a stablecoin called USDx, provided by AnchorUSD.

USDx is an "asset" on Stellar provided by AnchorUSD. If a user wishes to buy USDx, they must undergo the checks required by AnchorUSD, transfer money to AnchorUSD, and receive USDx in their account. They can also purchase USDx using the Stellar DEX. USDx can be used to invest in projects that platforms advertise for funding, like opensolar.

### CI

A basic CI that builds the openx and opensolar executables is available as part of openx. This can be modified to build any executable. There is also a frontend inspired by Go Downloads, which offers users a clickable interface to download the executables.

For more information on how Stellar integrates with Opensolar, checkout the "Opensolar on Stellar" doc in the wiki.

