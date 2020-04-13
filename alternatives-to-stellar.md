---
description: >-
  This page describes and analyses how the platform functions, and suggests
  suitable alternatives.
---

# Alternatives to Stellar

Recommended previous reading: [https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29](https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29)

## Introduction

Opensolar is a platform for investments in solar energy projects. Opensolar's initial prototype was in Ethereum, and currently uses the Stellar blockchain. In this document, we will explore key advantages and disadvantages of using Stellar, along with other alternative blockchain ecosystems that Opensolar could potentially use.

## Advantages of Stellar

Stellar has the following advantages for opensolar:

1. **Fast and cheap payments:** Stellar transactions are confirmed within 5 seconds and the transaction cost is low \(defaults to 0.00001 lumens or 100 stroops per transaction\). Transactions are final once they are in a block thanks to Stellar's Consensus algorithm, removing the need for handling re-orgs as would occur in a Proof of Work blockchain.
2. **Easy asset creation:** Stellar makes it extremely easy to create new assets and transfer them between addresses. This makes representing state variables easier and  enables the creation of secondary markets where users can exchange one asset for another.
3. **Horizon API:** Stellar's Horizon API makes it easy to query and post to instances that are full nodes. The API also gives a good interface to build transactions and do operations that change the state of accounts on the blockchain.
4. **Testnet that mimics mainnet:** The Stellar Development Foundation mimics mainnet on a testnet that it runs, making it very easy to test features before deploying to mainnet. It also maintain a testnet faucet to get test lumens from, making easier the process of creating new accounts.

## Alternatives to Stellar

While Stellar is good in terms of what it offers, it comes with a few disadvantages:

1. **Limited opcode set:** Stellar's list of possible operations is extremely limited, possessing only those operations that are relevant in a payment/funds transfer setting. This makes development of verifiable contracts harder.
2. **Questionable Security:** Stellar's mainnet and testnet have been down for multiple hours in the past, and Stellar's quorum based consensus algorithm has a side effect of nodes trusting the Stellar Development Foundation's nodes since its enabled by default. This increases dependency on the Stellar Development Foundation to not act maliciously, reducing security and decentralisation.
3. **Small Number of Full Nodes:** The number of full nodes on the Stellar blockchain is limited \(~140\), making it easier for entities to collude and censor transactions.
4. **Absence of verifiable on chain computation:** Stellar does not possess an on chain smart contract validation / transaction execution validation mechanism.
5. **Limited ecosystem resources and lack of exchange liquidity:** Though Stellar was started in 2014, it has failed to gain traction in terms of Stablecoin adoption, Merchant adoption, and widespread adoption. The liquidity in popular markets for Stellar-native stablecoins is low, making large scale investments in projects \(&gt; $10000\) difficult.

Given these disadavantages, it is useful to explore alternatives that may address some of these concerns.

### Goals

The platform has a set of goals which can be used to compare different blockchain ecosystems:

* **Trustless:** The platform must minimize trust in itself to avoid attack vectors centred around it.
* **Secure and Decentralised:** The platform must be backed by a secure blockchain without the possibility of attacks either by a coordinated hash power or by a small group of attackers.
* **Robust in functions:** The platform must be able to perform its intended set of functions in an easy, fast and secure manner without compromising on provided functions.
* **Good partner ecosystem:** Users must be able to get on the platform as easily as possible with minimal steps required.

More steps along with sample ratings are outlined at [https://docs.google.com/spreadsheets/d/1H6HwnCwCMZ1yMZqEkVnr2Pw777mmAwhBQHiX1vnC9VM/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1H6HwnCwCMZ1yMZqEkVnr2Pw777mmAwhBQHiX1vnC9VM/edit?usp=sharing).

In this document, contentious blockchains like Bitcoin Cash and Bitcoin SV whose development is highly volatile and centralised to a limited number of people in the ecosystem are omitted. Blockchains like Tron, Ripple, and EOS whose development and funding goals aren't clearly defined are also omitted.