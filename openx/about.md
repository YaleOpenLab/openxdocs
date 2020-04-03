---
description: A description of the openx/opensolar interaction and architecture
---

# About

#### Introduction

Openx is a "platform of platforms" architecture for investments using blockchains. Openx is built using the Stellar blockchain but its modular architecture enables it to be used with any blockchain. Openx provides a set of functions for platforms that build on top of it, composed of the following parts:

1. A Smart Contract that performs the core functions of the platform 
2. A JSON-RPC interface through which the frontend and other pieces of software can interact with the backend.
3. Auxiliary packages that handle functions like KYC, Stablecoins, different Investment models, etc

The functionality associated with each package within the platform is exposed through a JSON-RPC API. This API follows a token based authentication scheme which callers can invoke. Openx also provides auxiliary features through its API that platforms might find useful like Know Your Customer (KYC) functionality and AML screening powered by ComplyAdvantage.

Openx platform skeletons can be easily created using the CLI based tool create-openx-app, or can be forked from the main opensolar repository. Platform skeletons are designed in the same fashion as openx, to be modular and scalable in its architecture.

There is one entity on the openx platform that acts as a parent entity for entities on other platforms - the "User" entity. This entity contains fields that are required for maintaining cross-compatibility with other openx based platforms. It also contains handlers for all cryptocurrencies supported by openx, and platforms are highly recommended to import this functionality from openx.

As a rule, cryptocurrency operations and handling must take place within the parent openx platform. If platforms would like to add support for other cryptocurrencies, such functionality must be added to the openx repository to enable cross openx platform investments. This is to ensure that users in openx based platforms do not worry about security of the platform, and can refer to openx's central contract audits to build confidence in the platform.

Openx uses boltDB, a key value pair database for its internal storage, in order to store user credentials, encrypted user seed, and more. It also uses IPFS to store bigger ceredentials that platforms might need.

Openx also provides a CI-enabled build server that can be used to release platform builds for different platforms. This function is used by openx internally to provide pacakges for its own releases at builds.openx.solar.

Openx also has a PPA to enable easy installation for linux users. This is easily configurable to use by other platforms as well.

### Stellar

Openx primarily uses Stellar, a Proof of Stake blockchain based on the Stellar Consensus Protocol. Stellar follows an account based model of accounting in which balances are associated with a public key \("account" or "address"\) on the blockchain, and subsequent operations increase the balance associated with the address. Stellar provides a set of operations that can be performed globally to change the state of a set of addresses \([https://www.stellar.org/developers/guides/concepts/list-of-operations.html](https://www.stellar.org/developers/guides/concepts/list-of-operations.html)\)

Stellar's blockchain interface has two components:

* [Stellar-core](https://github.com/stellar/stellar-core): Stellar core is the blockchain client that communicates with other nodes and takes part in the Stellar Consensus Protocol.
* [Horizon](https://godoc.org/github.com/stellar/go/clients/horizon): Horizon is the API instance of stellar-core used to interact with the blockchain.

Openx right now connects to the Stellar Development Foundation's Horizon instances, although an openx platform can choose to run its own node or connect to other Horizon instances. This however, would not provide much additional censorship resistance since the quorum that the Stellar Consensus Protocol depends on for consensus relies by default on the SDF nodes.

### Users

Users can undertake multiple roles in an openx-powered platform:

* Investors
* Recipents,

and more depending on a platform's utility. Openx leaves the requirements for these roles to the builders of a platform.

Users in openx can be of two types:

* **Individual accounts:** Individual aaccounts are held and represented by one individual.
* **Company accounts:** Company accounts are held by one individual but the account represents a company. KYC requirements for a company account differs from that of an individual account.

More types can be defined in the future if required \(platforms can define more types as well\)

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

Admins are trusted entities who ideally should be the same as those running the platform on the cloud instance. Admins however, do not have access to any user account and can not perform functions like resetting passwords or investing in projects.

### Stablecoins

Stablecoins are digital representations of fiat currencies. Common examples are Tether, USDCoin and more. Stablecoins are usually based off Bitcoin or Ethereum but since openx builds on top of Stellar, it uses a stablecoin called USDx, provided by AnchorUSD.

USDx is an "asset" on Stellar provided by AnchorUSD. If a user wishes to buy USDx, they must undergo the checks required by AnchorUSD, transfer money to AnchorUSD, and receive USDx in their account. They can also purchase USDx using the Stellar DEX. USDx can be used to invest in projects that platforms advertise for funding, like opensolar.

### CI

A basic CI that builds the openx and opensolar executables is available as part of openx. This can be modified to build any executable. There is also a frontend inspired by Go Downloads, which offers users a clickable interface to download the executables.

For more information on how Stellar integrates with Opensolar, checkout the "Opensolar on Stellar" doc in the wiki.

