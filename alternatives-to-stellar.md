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

## Bitcoin

Bitcoin is the oldest cryptocurrency, powered by a Proof of Work consensus mechanism. Bitcoin uses an unspent transaction output \(utxo\) model and individual utxos are transferred between multiple addresses. Bitcoin possesses a native scripting language called Bitcoin Script which can be used to model different functions on Bitcoin.

## Ethereum

Ethereum uses an account based model similar to Stellar. Ethereum provides a Turing complete on chain smart contract abstraction \(called the Ethereum Virtual Machine or EVM\) and global state variables. This eliminates the need for assets on Ethereum. As a consequence, the opensolar smart contract which runs on AWS could migrate to the Ethereum blockchain.

Ethereum provides a wide range of opcodes to work with, and arbitrary functionality can be implemented. Ethereum charges "gas" for each computation performed on chain. For common operations like hashing, adding, multiplying and state updates, Ethereum fixes the amount of gas that is charged. For other operations, a variable amount of gas is charged. Transaction fee is denominated in ETH. Gas and ETH are subject to their own fee markets.

The EVM is a powerful abstraction for developers developing on chain smart contracts. Running smart contracts on chain provides provable execution without having to provide commitment proofs for computation. An on chain smart contract also improves auditability of a contract since one can easily check if the code on the repository is the same as the code deployed on the blockchain. This enables third party monitors to monitor updates / investments on the platform. Third party services can also create their own web interface, and for the contract to create their own instance of Opensolar.

Ethereum has a large developer ecosystem and lots of potential ideas and applications that can be used without much effort. These applications can augment the platform and enable the intersection multiple ideas.

Ethereum has L2 solutions similar to Bitcoin \(eg. Plasma\). Ethereum is transitioning to a Proof of Stake system where miners stake ETH to take part in consensus instead of hashing. Ethereum also has provisions to incentivize developers to work on projects through decentralized crowdfunding ideas \(example Gitcoin\). This could be a mechanism to fund development and bounty programs on opensolar.

### Sharding

Sharding is a distributed systems idea where a single piece of data is split into multiple pieces and consistency is managed by an algorithm that communicates with the different pieces. Splitting data reduces data storage requirements, increases local read/write speed, and efficiency of individual shards. Each shard ultimately communicates with the other shards either during a fixed time interval \(eg: once in 30 seconds\) or through a protocol.

Ethereum has a big archival storage requirement due to a need to store state updates of all deployed and inactive contracts. Sharding Ethereum's storage provides faster transaction confirmation, and reduces storage requirements for running an Ethereum node. It also enables a shard to have its own set of rules, and these rules need not be reflected or communicated to the parent Ethereum blockchain.

For opensolar, one could use a two layer shard architecture where each platform lives on its own shard with its own set of rules, and communicate with a bigger openx shard which commits to the Ethereum blockchain. State updates can be fast, local and free, and proofs can be given to different entities once the platform once the parent openx shard commits to the Ethereum blockchain.

Like Bitcoin sidechains, this requires a shard explorer to navigate through the different shards. The shard explorer should contain details of a transaction or state update along with the block in which the openx shard committed the particular change to the parent Ethereum blockchain.

Shards need not necessarily be Ethereum based, they could even be different blockchains whose headers commit to the parent openx shard and/or the Ethereum blockchain.

The trust model for this involves trusting the openx shard and the platform shard, along with the parent Ethereum blockchain. If a shard owner tries to cheat an entity, the entity can submit proofs to ruin the platform's reputation.

### Advantages

1. **Low Fees:** Each shard can process transactions faster and cheaper since the shards communicate with each other only at certain intervals.
2. **Big partner ecosystem:** Ethereum has a large number of partner companies looking to improve different aspects of using and getting on to Ethereum.
3. **More secure and decentralised:** Shards are easy to run and the requirement to become a shard validator is not too high. The number of nodes running Ethereum full nodes is around 6000 and the number of shards will only be more, making it more decentralised than Stellar.
4. **Improved functionality:** Since shards replicate the functionality of Ethereum-L1, the EVM and other features are available on any shard.
5. **Faster transactions:** Transaction processing is split into multiple shards and each shard can process the same amount of transactions faster since there are more processing units to process them.

### Disadvantages

1. **Not time tested:** Sharding is not a new idea but implementations of sharding in the blockchain space have not been tested for security and performance.
2. **Need to handle shard commitments, updates and malicious behaviour:** There is a possibility that a participant in the platform coordinates with shard validators to defraud the platform or the platform can coordinate with validators to defraud entities. Attack scenarios need to be modelled and tested carefully before deployment.
3. **Compatibility with Beacon Chain:** It is unclear how compatible Sharding will be with the Ethereum PoS upgrade.

### DeFi and algorithmic stablecoins

DeFi or decentralized finance seeks to replicate existing financial technology applications on top of Ethereum. Common applications are loans, lending, stablecoins, arbitrage, etc and product examples are sDAI, mDAI, Gitcoin, Liquidity protocol and Uniswap.

A potential usecase is chaining these applications and using the combination to invest in projects on the platform. As an example, an investor can use ETH as collateral to obtain a USD loan to invest in projects. A recipient could advertise projects that deposit real world collateral in exchange for short to medium term loans. Recipients can list their projects on Gitcoin, and ask for funding from the Ethereum community, and investors in such projects can receive returns through the platform.

This model would have to be supplemented by a base layer blockchain which handles non-financial infrastructure. This could be Ethereum-L1 or other blockchains and openx would need to support various Ethereum operations in order to be compatible.

The trust model for this depends on the chain of applications \(eg. for DAI, you trust the algorithm to keep the peg, for Gitcoin you assume there are no bots trying to game the system\).

### Advantages

1. **Easy onboarding and big partner ecosystem:** DeFi applications are available in a variety of countries and local onboarding is easier.
2. **More financial functionality:** Since there is more scope for moving assets around, financial fnctionality of the platform can be enhanced.

### Disadvantages

1. **Hacks:** Many DeFi applications are unaudited and as a result, are prone to hacks. One must carefully vet the smart contract of a DeFi application before putting it to use in a production setting.
2. **Need to trust entities providing these applications:** Some DeFi applications are governed by different foundations, and entities on the platform would have to trust these entities to not act maliciously, to not close the smart contract, etc. \(eg. The Maker Foundation in the case of MakerDAO\)

### Decentralised Autonomous Organisations

A DAO is a decentralised organisation where the participants have a say on a list of proposals before the DAO depending on the amount they have staked in the DAO. This enables decentralised applications of centralised systems like voting and community participation to happen with anonymity and privacy.

A DAO can be used by entities to vote on project timelines, to vote on whether they are satisfied with the project's deployment, to vote on what projects to include on the platform and more. It could also be used when deciding on the timeline of the platform's development, who's responsible for developing the platform, etc.

This model would have to be supplemented by a base layer blockchain which handles the non governance part of the infrastructure. The base layer should be Ethereum-L1 since only then can people vote or stake on proposals with ETH. Having a different base layer blockchain would mean that people deal with three types of currencies - a stablecoin, ETH and the base layer blockchain's native coin.

The trust model is that one trusts the algorithm the DAO is based on to take actions based on the majority of votes cast for or against a proposal.

### Advantages

1. **More decentralised than Ethereum-L1**: The barrier of entry to a DAO is low and as a result, people can easily participate in DAOs. This means more people partake in governance resulting in a better platform.
2. **More participation functionality:** Since a DAO enables new forms of participation, the platform could expand on governance related functions.

### Disadvantages

1. **Hacks:** Like the famous case of TheDAO, DAOs are a double edged sword and must be carefully vetted before putting it to use in a production setting.
2. **Over-application:** In some cases, having a DAO slows the decision making process. The desire to involve the community in everything must be intricately balanced with the need for a fast decision making process.

### Bridges

Ethereum offers bridges to other cryptocurrencies like Bitcoin. These bridges could be used to construct a dual layer commitment system where proofs exist in two blockchains. Bridges can also offer a choice between two chains depending on the fee, atomic swaps with other chains using the smart contract, and more.

In essence, a bridge is like having two-L1 blockchains to commit to and the trust model is dependent on the least secure of the two blockchains along with the bridge's smart contract.

### Advantages

1. The advantages of bridges is a combination of the blockchain systems it is based on.

### Disadvantages

1. Need to trust entities providing the bridge, and the smart contracts powering the bridge.

### Layer 1 Ethereum

Ethereum's EVM offers a powerful on chain smart contracting interface. This can be used to offer verifiable contract execution on chain, global state variables, etc.

The platform's contract can be deployed on chain and entities would interact with the contract through standard tools available on Ethereum. Investment proofs, state variables are all stored on chain so there is minimal requirement for an in house database that serves these functions.

Ethereum-L1 can also be used in parallel with blockchain system. For example, payments can take place on Bitcoin, and state updates and storage can take place via Ethereum. This gives the dual benefit of low fees while still having auditable smart contracts on chain. This case is a slight variation of the bridge scenario described earlier.

### Advantages

1. **Better security and decentralisation:** Due to Ethereum's PoW consensus model, it is extremely expensive for an attacker to attempt to censor or rewrite transactions.
2. **Big partner ecosystem:** Ethereum has a large number of partner companies looking to improve different aspects of using and getting on to Ethereum.
3. **Improved functionality:** Ethereum's EVM provides the ability to replicate any program on Ethereum thereby expanding the capabilities of the platform.
4. **Good Liquidity:** Ethereum is the second most traded cryptocurrency asset. Hence liquidity on popular markets is not of concern.
5. **On chain verification:** The EVM provides an easy mechanism to verify computation on chain.

### Disadvantages

1. **High Gas and Transaction Fees:** Ethereum transaction fees depend on the gas market, which fluctuates depending on the usage of Ethereum. Frequent state updates on the contract are expensive, and commitments must be timed to reduce overall costs involved.
2. **High Complexity:** Due to the EVM's complexity, there are multiple avenues for unexpected results, hence a thorough audit is required before using a contract in production.
3. **Uncertainty due to Proof of Stake shift:** Since Ethereum is shifting to a PoS system in the near future, it is unclear if all the functionality of Ethereum-L1 will be preserved in the new chain. It is also unclear if new smart contracts need to be developed for the PoS chain, or whether the PoS chain will be backward compatible.

## Cosmos

Cosmos is a proof of stake blockchain with an aim to be the "blockchain of blockchains" by enabling connections to multiple other blockchains. Cosmos' modular architecture enables multiple openx platforms to communicate with each other by connecting to different nodes that offer services on Cosmos.

## Hyperledger

Hyperledger is an open sourced permission blockchain system. Hyperledger's permission model allows only certain nodes to run, and these nodes are held accountable. Hyperledger has two main implementations - Hyperledger Fabric and Hyperledger Indie.

## Polkadot

Polkadot is a spin-off from Ethereum's original Web3.0 ideas. Polkadot, similar to Cosmos, wants to enable bridges to other cryptocurrencies and serve as a connecting layer for blockchains.

