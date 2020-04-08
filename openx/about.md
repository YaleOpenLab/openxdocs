---
description: This section describes openx and how it functions
---

# About

### Introduction

Openx is a "platform of platforms" architecture for investments using blockchains. Openx is built using the Stellar blockchain but its modular architecture enables it to be used in combination with any blockchain. Openx provides a set of functions for platforms that build on top of it composed of the following parts:

1. A Smart Contract that performs the core functions of the platform.
2. A JSON-RPC interface through which the frontend and other pieces of software can interact with the backend.
3. Auxiliary packages that handle functions like AML screening, stablecoin support.

The functionality associated with each package within the platform is exposed through a JSON-RPC API. This API follows a token based authentication scheme which callers can invoke. Openx also provides auxiliary features through its API that platforms might find useful like AML screening powered by ComplyAdvantage.

Openx platform skeletons can be created using the CLI based tool create-openx-app, and a live platform can be forked from Opensolar. Platform skeletons are designed like openx to be modular and scalable.

There is one entity on openx that acts as a parent entity for entities on other platforms - the "User" entity. This entity contains fields that are required for maintaining cross-compatibility with other openx based platforms. It also contains handlers for all cryptocurrencies supported by openx, and platforms are highly recommended to import this functionality from openx.

As a rule, cryptocurrency operations and handling must take place within the parent openx platform. If platforms would like to add support for other cryptocurrencies, such functionality must be added to the openx repository to enable cross openx platform investments in the new cryptocurrency. This is to ensure that users in openx based platforms do not worry about security of the platform, and can refer to openx's central contract audits to build confidence in the platform. This is also to encourage the idea of open innovation where people can collaborate on building something big.

Openx provides a rescue tool to use in the event the platform is down, or someone is trying to hack the platform. This rescue tool can be used to sweep funds belonging to the platform to another address quickly. This tool also enables assets like USD if the caller can specify the asset's name to the tool.

Openx uses boltDB, a key value pair database to store user credentials, encrypted user seed, and more. It uses IPFS to store bigger ceredentials that platforms might need.

Openx also provides a CI-enabled build server that can be used to release platform builds for different platforms. This function is used by openx internally to provide pacakges for its own releases at builds.openx.solar.

Openx also has a PPA to enable easy installation for linux users. This is easily configurable by other platforms as well.

## Stellar

Openx uses Stellar, a Proof of Stake blockchain based on the Stellar Consensus Protocol. Stellar follows an account based model of accounting in which balances are associated with a public key \("account" or "address"\) on the blockchain, and subsequent operations increase the balance associated with the address. Stellar provides a set of operations that can be performed globally to change the state of a set of addresses \([https://www.stellar.org/developers/guides/concepts/list-of-operations.html](https://www.stellar.org/developers/guides/concepts/list-of-operations.html)\)

Stellar's blockchain interface has two components:

* [Stellar-core](https://github.com/stellar/stellar-core): Stellar core is the blockchain client that communicates with other nodes and takes part in the Stellar Consensus Protocol.
* [Horizon](https://godoc.org/github.com/stellar/go/clients/horizon): Horizon is the API instance of stellar-core used to interact with the blockchain.

Openx right now connects to the Stellar Development Foundation's Horizon instances, although an openx platform can choose to run its own node or connect to other Horizon instances. This however, would not provide much additional censorship resistance since the quorum that the Stellar Consensus Protocol depends on for consensus relies by default on the SDF nodes.

## Users

Users can undertake multiple roles in an openx-powered platform:

* Investors
* Recipents,

and more depending on a platform's utility. Openx leaves the requirements for these roles to the builders of a platform.

Users in openx can be of two types:

* **Individual accounts:** Individual aaccounts are held and represented by one individual.
* **Company accounts:** Company accounts are held by one individual but the account represents a company. KYC requirements for a company account differs from that of an individual account.

More types can be defined in the future if required \(platforms can define more types as well\)

## Platforms

Platforms in openx refer to platforms that build on top of openx and enable investments in a specific asset class. Opensolar is an example of a platform \(Opensolar enables investments in solar energy projects\) built on openx.

Platforms are independent entities that do not affect the base openx platform. Users having an openx account can simultaneously invest in multiple platforms if they have funds in the required currencies. Users on a platform can choose to be any entity as defined by the constructs of the platform. These roles are not reflected on openx.

Platforms building on openx need to be registered and need to obtain a unique code that enables them to use the platform-platform openx API. This API grants access to a privileged set of endpoints and allows platforms to create new openx users, retrieve data related to openx users, get openx constants and more.

## Administrators

Openx has support for platform admins who can perform functions like

* Seeing all users on the platform
* Manually enabling KYC for a user
* Banning a user
* Sending emails to users
* Create new platform registration codes

Openx Admins are trusted entities who are in charge of the openx project. Platform admins should be those having access to the server where the platform's contract is running. Admins do not have access to user accounts however, and can not perform functions like resetting passwords or investing in projects.

## Stablecoins

Stablecoins are representations of fiat currencies on blockchains. Common examples are Tether, USDCoin and more. Stablecoins are usually based off Bitcoin or Ethereum but since openx uses Stellar, it uses a stablecoin called USDx, provided by AnchorUSD.

USDx is an "asset" on Stellar provided by AnchorUSD. If a user wishes to buy USDx, they must undergo KYC checks required by AnchorUSD, transfer money to AnchorUSD, and receive USDx in their account. They can also purchase USDx using the Stellar DEX. USDx can be used on platforms which use Stellar and advertise for investments in USD.

## Continuous Integration

A basic CI that builds the openx and opensolar executables is available as part of openx. This can be modified to build any executable. There is a web interface for downloading these executables inspired by Go Downloads, providing users with a clickable interface.

