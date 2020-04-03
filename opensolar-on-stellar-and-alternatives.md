---
description: >-
  This page describes and analyses how the platform functions, and suggests
  suitable alternatives.
---

# Opensolar on Stellar, and alternatives

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

### Layer 2

Layer 2 \(L2\) is a term used to describe scalability and functional improvements that occur parallel to the main blockchain. L2 based solutions often commit to the main blockchain at certain intervals or when certain criteria are fulfilled.

Popular L2 improvements on top of Bitcoin are the Lightning Network and Sidechains. Popular L2 improvements on top of Ethereum are Sharding and Plasma.

### Lightning Network

The Lightning Network \(LN\) is a peer-peer L2 payments layer. It offers fast and trust minimised payments that can be adapted to a variety of applications by changing the architecture of the system.

Each "peer" \(or "node"\) in Lightning is a user who either runs their own node or communicates with one. Each peer is required to have atleast one channel with another peer to pay others on the lightning network. The lightning network also has a native routing protocol which can route payments from one peer to another.

Payments are facilitated by peer to peer channels. Each peer has a balance associated with each of its channels, and the net balance of the channel is the sum of both peers' balances. Channels can be one or two way depending on the balance of each peer at each side of the channel. The ability of a given peer to pay another peer depends on the balances of peers in between, also referred to as the "liquidity" of a given route.

The lightning network requires liquidity from both peers in order to be effective. For a given peer, there are two types of liquidity - inbound liquidity and outbound liquidity. 

Inbound liquidity is the capacity with which a peer can be paid by other peers. The net inbound liquidity which is the sum of all individual inbound liquidities is the maximum amount a peer can be paid through lightning.

Outbound liquidity is the capacity with which a peer can pay other peers. The net outbound liquidity which is the sum of all individual outbound liquidities is the maximum amount a given peer can pay other peers through lightning.

Depending upon their role, a peer \(merchant, customer, payment processor, etc\), can optimise their outbound liquidity. To have inbound liquidity and to be reachable by other nodes, they would have to form networks with other peers on the network.

Peers can create invoices in the form of QR codes or text messages. An invoice communicates to the payee the details of the requester. An invoice can be fulfilled by any peer as long as they can find a route to the requester. Peers can also send text messages using the lightning network by paying nodes to route the messages.

A state in lightning is a cryptographic proof reflecting each peer's balance in a channel. In the event a peer acts maliciously, this proof can be published on Bitcoin-L1 and the malicious peer loses all their funds in the channel.

### LN Hub and Spoke Model

In the Hub and Spoke model, the platform \("Hub"\) acts as a centralized hub with which all the entities \("Spokes"\) in the platform interact and have channels with. The hub provides outbound liquidity to all spokes, coordinates payments and handles state updates. The platform does not expose public keys and channel ids, and handles lightning channels and state updates internally. This reduces the possibility of attacks by entities since they don't have a copy of their state \(only the platform does\). This however, this increases trust and responsibility on the platform since the platform should maintain these states in a stable manner, ensuring that no entity defrauds the other. The platform could also hire a watchtower's services in order to provide guarantees on users' channels not closing due to internal platform errors.

When users sign up on the platform, the platform could open an outbound channel with them and provide a fixed amount of liquidity. Users can add funds to channels by using Submarine Swaps or splicing funds into the channel if they choose to invest in a project.

Submarine swaps is a technique by which users can send altcoins to a specific altcoin address and atomically, a transaction funding a channel on lightning is broadcast to Bitcoin-L1. Splicing funds into a channel is done by closing a channel, adding an extra input and opening a channel, all in the same Bitcoin-L1 transaction. A channel can be funded by a number of means, and any can be used as long as the investor manages to successfully create / add funds to a channel with the platform.

An alternate proposition is to not have a channel unless an investor decides on investing in a project. The disadvantage with this approach is that investors have to wait for the transaction to be reliably confirmed before the platform can confirm their investment.

An investor creating a channel or pushing funds to the platform would have to push extra funds above the amount they wish to invest to cover for on chain fees of creating a channel, and to cover the channel closing transaction in the future. Therefore, the project's desired funding goal should include a small buffer.

For other entities, the platform opens a channel if and once the project they are associated with is funded. This prevents the need to deal with channels that aren't being used. The platform should close channels by default if a new state update has not occurred in the past 3/6 months to efficiently manage liquidity and to minimise attack vectors surrounding liquidity. If a project's expected time to reach the funding threshold is greater than this period, the channel should be kept open until this time elapses.

Once a channel is in place, the investor pushes the amount they wish to invest towards the platform. When the total amount invested reaches the project threshold, the platform opens a new outbound channel with the receiver, developer and other entities, the project is marked complete, and the investor is given the transaction ids of the channels that the platform newly opened. The platform pushes back a small amount of funds back to the investor to update the last known state. The investor could also choose to transfer some small amount funds back to the platform through additional investment or through donations in order to bury the bigger investment within the list of states. This increases the effort required by a malicious platform admin to defraud them.

After completion of investment, the investor could choose to close the channel but closing and opening a new channel each time an investment is completed or initiated has no difference \(and in some cases, is more expensive\) compared to a standard Bitcoin-L1 transaction. The platform could potentially detect user behaviour and recommend on-chain funding if the fee is low, if a given investor does not plan on investing in more than one project, or if the amount of investment is sufficiently high to warrant the high transaction fee on Bitcoin-L1.

With the newly established outbound channel, the platform and receiver collaborate to send funds to different entities \(the platform should cooperate by default\). If the receiver wishes to pay the developer, it tells the platform that it wants to push funds to the developer and the platform will push funds through its channel with the developer. Alternatively, the platform can push funds towards the recipient and the recipient can choose to route funds through the platform or other means to the developer. The receiver could also receive LN payments from the platform and pay the developer off chain, and provide confirmation by adding the receipt to stage data.

Guarantors need to open a channel with the platform \(or top up the balance on their end towards the platform\) and in the event the receiver fails to pay, the guarantor should push funds towards the platform and the platform will treat this as a normal payment from the receiver while keeping note and sending notifications to all parties on the platform that the receiver has defaulted on a payment.

An alternate route for investments in projects is that a receiver provides an invoice which the investor funds through a non-openx account. The platform and the receiver should still be able to pay the investor back since the platform can scan the public key of the investor from the blockchain. This also enables donation projects where investors look to donate funds to different projects through the Bitcoin Lightning Network.

Investors holding altcoins can use atomic swap services \(which could either be facilitated by the platform or by a third party service\) or submarine swaps to invest in projects. This expands the reach of the platform beyond Bitcoin.

The platform should take note of griefing attacks \(ie\) when users sign up as receivers or developers but don't use the account, effectively forcing the platform to lock funds for a pre-defined period of time. This can be avoided by only opening channels with entities that are already associated with a project, and by efficiently closing unused channels.

The trust model in this scenario is that entities trust the platform to push funds to the developer, contractor, create multisig escrows, etc. The availability of proofs in the form of state update hashes and tx ids removes the need for state variables.

### Advantages

1. **More Secure and Decentralised:** There are more people running Lightning nodes than Stellar nodes. Lightning relies on Bitcoin-L1 for security, ensuring a high safety margin for investments.
2. **Faster payments:** Since Lightning transactions are settled immediately, this is faster than having to wait for a block. Lightning transactions can also be asynchronous since there are multiple channels open at the same time.
3. **Good partner ecosystem:** Many partner companies are available in the Lightning ecosystem and it is easy to leverage their help to improve the functionality of Opensolar. Building on Lightning would also enable the possibility of lightning mobile apps - web platform cross integration, making it easier for receivers to pay back towards projects.
4. **Improved Functionality:** Lightning offers more functionality \(atomic swaps, state update proofs\) that Opensolar could expand on compared to Stellar, and Lightning core development is faster than Stellar.
5. **Option to switch between Bitcoin-L1 and Lightning:** For high valued investments, it is easy to leverage Bitcoin-L1's security.

### Disadvantages

1. **Need to manage liquidity:** Since the platform acts as a central provider of liquidity, it maintains a non trivial balance of Bitcoin in open channels and it should manage these balances efficiently. Failure to manage balances efficiently could lead to the platform's inability to open new channels and therefore increase costs. Maintaining channel balances also means there's an amount that is constantly locked and not spendable.
2. **Need to handle channel closing:** Since lightning is a channel based infrastructure, the platform should be adequately equipped to handle channel closures \(both by the platform, and by the entities on the platform\). An alternative might be that the platform does not offer channel closures to entities on the platform though this comes at the cost of reduced decentralisation.
3. **Handling large payments:** Lightning is still in its infancy with respect to channel capacity and large amounts that need to be transferred sometimes fail to find a route. One way to handle this is by ramping up channel capacity on the platform's end as needed although this would conflict with 1 above, and make liquidity handling more difficult.

### Pre-signed Transactions Model

A bitcoin transaction requires signatures from all private keys associated with input utxos. A transaction can be broadcast to the blockchain at any time provided the spending conditions and associated signatures are still valid at the time of broadcast. As a result, a transaction can be signed beforehand but broadcast when required. Such a transaction is referred to as a "pre-signed transaction". This transaction can have conditions associated to spending \(for example, invest 1000 in this project within 3 months, else refund money to this other address\) that refund to a user if not broadcast within a certain interval of time, can have locktimes that automatically render the spending conditions invalid, etc.

If an investor wishes to invest in a project, they could give a pre-signed transaction to the platform guaranteeing their investment if it reaches the investment threshold. If the investment threshold is reached, the platform checks if the spending conditions and signatures are valid, checks the blockchain to see if the txos are still unspent, and broadcasts the transaction. The investor can also add conditions to investments which are a combination of project conditions and blockchain rules \(example: if this project raises atleast 10000 within 1 month, invest 4000 else wait for project investment and refund after 3 months if project threshold is not reached\), and the platform would check if these are valid at the time of broadcast.

The platform on completion of investment signs transactions paying funds to the developer and contractor but does not publish them until the receiver has marked their role complete and provides proof that the installation was complete. The guarantor gives pre-signed transactions that the platform agrees to not publish unless the receiver defaults on a number of payments.

In the event the investment threshold is not reached, the investor should spend the funds associated with the address to another address or should specify a refund address to the platform. The latter places responsibility for broadcasting the refund transaction onto the platform and the former places emphasis on the investor to transfer their funds as soon as their deadline for investment has is reached.

This model would involve the construction of a secure way to store pre-signed transactions since any user in possession of them can broadcast the transaction, and gried users if they act maliciously. One time passcodes that are relayed on completion of certain events to encrypt the transactions are a potential solution to this problem.

The trust model of this idea relies on the platform not grief attacking its users and not broadcasting funds. At most, the platform has the ability to selectively censor txs, prevent recipients from getting money, etc.

### Advantages

1. **Easy proof handling and refund system:** Giving an entity proof of a transaction is as simple as giving the hash of the pre-signed transaction id. When the transaction is broadcast, the entity can see the transaction on the blockchain, take the hash and compare it with what they had to ensure they weren't defrauded. Refunds are also easy to process since they only involve the deletion of the pre-signed transaction
2. **Security and Decentralisation of Bitcoin-L1:** Due to Bitcoin's high PoW, a pre-signed transaction that is broadcast can almost never be reversed if the receiving entity waits for a given period of time.
3. **No stablecoin:** This model does not involve a stablecoin, and people need not trust third party vendors.
4. **Big partner ecosystem:** Bitcoin has a lot of partner companies which are looking to improve different aspects of using and getting on to Bitcoin. Since the model does not use a stablecoin, the platform can build more on core Bitcoin functionality without worrying about third party stablecoin providers
5. **Improved functionality:** Bitcoin has more opcodes than Stellar, and can therefore the platform can look to implement more complex functionality.

### Disadvantages

1. **Less decentralised than Lightning:** Since the platform possesses pre-signed transactions, a malicious platform could refuse to broadcast or delete the transactions, grief attacking the entities involved in the transaction. Although such an attack would come at a reputational risk to the platform, this places more trust on the platform than Lightning.
2. **Slow confirmation times:** Bitcoin transactions are slower than Stellar transactions, so the platform needs to wait for a given period of time before it can confirm an investment or withdrawal.
3. **High Fees:** Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin. Since this model does not make use of a stablecoin, the fees associated with a stablecoin is discounted and more than accounts for any Bitcoin transaction fee involved.

### Sidechains

Sidechains are similar in design to the Lightning Network and act as a parallel layer for settlement of transactions. They however, differ in architectural construction since they don't have channels or liquidity. Sidechains' design is the same as Bitcoin-L1 except that the block headers are committed at regular intervals to Bitcoin-L1 or their blocks merge-mined along with Bitcoin-L1 with smaller commitments being made in parallel on the sidechain. A sidechain when viewed from the outside looks no different than a standard blockchain., and a platform that adopts Bitcoin-L1 can readily migrate to a sidechain by naking minimal changes.

A sidechain can provide an improved set of features \(eg: the block interval can be smaller, there may be no transaction fees associated with the sidechain, etc\). All bitcoin protocol rules valid in Bitcoin-L1 are valid in a sidechain based on Bitcoin, although a sidechain can be based off a different currency like Ethereum and commit state updates to Bitcoin-L1. A sidechain can also be a federated system, with certain entities having permissions to write to the sidechain and subsequently, Bitcoin-L1.

Each openx platform can be its own sidechain and a centralized coordinator can group the hashes and commit them at regular intervals to Bitcoin-L1. The parent openx platform could itself be a sidechain and different platforms based off openx can be children sidechains which commit to the parent openx sidechain. Functions inside the platform can be same as that on Bitcoin except they can be faster, cheaper and have more features added on to the base layer. Each individual platform need not worry about whether it is running on a sidechain or not since there is no distinction.

An alternate architecture would be one where each platform submits transactions and other changes to the bigger openx platform, and openx decides which sidechain to post the transaction to. Additional features \(that are not present on the Bitcoin base layer\) if used can be marked with flags. Openx can maintain an internal store of the transactions broadcast by a platform. Openx can also broadcast transactions without flags to Bitcoin-L1 depending on the amount transacted and the current fee market. Openx should return a proof to the caller platform \(ideally a tx id\) that the transaction was broadcast, along with a sidechain or Bitcoin-L1 identifier. This identifier can be used on a sidechain or Bitcoin-L1 explorer to identify the transaction.

A sidechain explorer should contain the details of the tx \(like a normal blockchain explorer\) along with the L-1 block the chain's headers were committed to. This way, entities in possession of the proofs can easily cross reference where their transactions were committed. In the alternate architecture, an explorer must display if the transaction was commit to Bitcoin-L1 or a sidechain, and provide an identifier for the same.

A sidechain could also be used in combination with another Bitcoin-L1 or another blockchain with each performing a subset of functions. The sidechain could be used as a layer for updating state and Bitcoin-L1 could be the layer where investments and payments happen.

The trust model for this depends on the sidechain's construction - who can create blocks, who can post transactions, etc. Since opensolar's idea revolves around trusting the platform, the platform can be the entity that performs these functions. Existing sidechains like Liquid or merge mined coins like RSK can also be used in place of a custom sidechain. The trust model for the latter is that one should trust the entities controlling these sidechains along with the platform.

### Advantages

1. **Improved Functionality:** Sidechains offer a wide range of functionality like smart contracts, asset and confidential transactions which can be used to improve platform functionality.
2. **Fast transactions:** Sidechain transactions are usually faster than Bitcoin-L1, and depending on construction, faster than Stellar.
3. **Easy integration with Bitcoin-L1 and Lightning:** Sidechain pegs are easy to get in and out of. Onboarding is therefore easier since one can leverage the partner ecosystem of Bitcoin to get into a sidechain.
4. **More secure decentralised than Stellar:** Sidechains usually have more running nodes than Stellar and therefore, it is less likely a transaction will be censored. Since sidechains are used in combination with Bitcoin-L1, sidechains borrow from Bitcoin-L1's security.
5. **Low fees:** Sidechains usually have negligible fees as compared to Bitcoin-L1, and sometimes, Stellar.

### Disadvantages

1. **External consensus mechanism:** The sidechain may have its own consensus mechanism and the attack vectors associated with this needs to be reviewed carefully.
2. **Deposits and Withdrawal delays:** When an entity wants to withdraw funds, they need to wait for the next commitment / merge mined block on Bitcoin, and subsequent confirmations on Bitcoin in order to withdraw their funds. This is usually slow since entities wait for a certain period of time before confirming a transaction on Bitcoin.
3. **Not time tested:** Sidechains are a relatively new idea, and their security has not been as time tested as Bitcoin. Sidechains however, have not suffered attacks like Stellar.

### Statechains

Statechains is an improvement on top of Sidechains, combining the Hub and Spoke model of LN with the semi trusted nature of Sidechains. Statechains requires a centralized coordinator which communicates with the others in the system, and an internal index that maps utxos to owners.

An entity that wants to enter a statechain can do so by creating a 2/2 Multisig address with the central coordinator "C". If "A" would like to transfer to "B" an utxo "X", it passes the private key "x" to B through C. C checks if A is indeed the owner of X, adds its signature and broadcasts it to the blockchain, and updates its internal map to reflect that B is the new owner of the utxo. A is required to delete the private key from its storage. Even if A maliciously stores the private key and attempts to spend it elsewhere, C refuses to sign the mutlisig transaction because its internal map shows that A transferred ownership of X to B at a point in the past. It could also penalise A for attempting to spend such an utxo by removing it from the statechain.

In Opensolar, the above can be mitigated by not exposing individual utxos to users. The platform can act as the centralised coordinator and investors can transfer utxos to the platform conditional on the investment threshold being reached. In the event the threshold is not reached, the utxo's ownership and the platform's itnernal mapping will not change.

Once the investment threshold is reached, utxos are transferred to an intermediary, and spending from the intermediary requires coordination between the receiver and platform. When the receiver wants to pay certain entities, it requests the platform to sign the transaction, and the platform subsequently transfers ownership of the utxo to the other entity.

Statechains can support multiple currencies that follow an utxo model, and users can choose to swap currencies within the statechain. This gives flexibility to the receiver, who can pay entities in other currencies.

Statechains requires Schnorr signatures as a minimum upgrade to the Bitcoin protocol. Statechains can also be used in combination with payment channels, and people can use these utxos to fund a channel between two peers.

The trust model for this idea relies on the platform not acting maliciously or in collusion with one of the previous owners of an utxo. In the event this occurs, proofs of ownership are easy to publish, and the platform's reputation will be at stake.

### Advantages

1. **Improved privacy:** Statechains have improved privacy compared to pre-signed transactions since the platform signs every transaction change request without discrimination. This interaction between entities and the platform can be made more private with Schnorr signatures.
2. **Support for altcoins:** Statechain coordinators can offer support for altcoins, enabling easy exchange of altcoins, stablecoins and Bitcoin within the platform.
3. **Security and Partner Ecosystem of Bitcoin-L1:** Statechains is an architectural expansion of Bitcoin-L1 and offers the complete security guarantees of Bitcoin-L1.
4. **No fees:** There are no fees associated with the transfer of utxos within a statechain since there are no Bitcoin-L1 transactions made.
5. **Fast transactions:** Transactions are almost instant on the statechain since there is no blockchain wait period involved.

### Disadvantages

1. **Less decentralised than Lightning:** Since the platform acts a a central coordinator for processing statechains, any of the previous owners of the utxo can collude with the platform to steal funds from a user. Such an attack will be public and does come at a reputational cost to the platform but the construction is more centralised than Lightning which does not have any such trust involved.
2. **Absence of assets:** Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets on Stellar. An alternative is to get rid of assets and handle only proofs.
3. **Slow confirmation times:** Bitcoin transactions are slower than Stellar transactions, so the platform can not afford to make a lot of synchronous payment requests during the investment workflow. This is a concern only when entering and exiting the statechain since transactions within the statechain are instantaneous.
4. **High Fees and whole utxos:** Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin. This would affect entities entering and exiting the statechain. Statechains also require complete utxos and splitting utxos should occur as a transaction on Bitcoin-L1, increasing fees and wait times involved.
5. **Not time tested:** Statechains is a recent development, and hasn't been battle tested for security.

### Bitcoin L-1

Similar to how things work on Stellar, the same transactions and workflow can be mirrored on Bitcoin.

### Advantages

1. **Good security and decentralisation:** Due to Bitcoin's PoW consensus model, it is extremely expensive for an attacker to attempt to censor or rewrite transactions. Bitcoin also has a large number of nodes \(&gt;10000\) which improves decentralisation.
2. **Big partner ecosystem:** Bitcoin has a large number of partner companies looking to improve different aspects of using and getting on to Bitcoin.
3. **Improved functionality:** Bitcoin has more opcodes than Stellar, and the platform can implement more complex functionality.
4. **Good Liquidity:** Bitcoin is the most traded cryptocurrency asset. Hence liquidity on popular markets is not of concern.
5. **On chain verification:** Bitcoin Script is verified on chain, and the platform need not be trusted for performing correct computation.

### Disadvantages

1. **Slow confirmation time:** Bitcoin transactions are slower than Stellar transactions, so the platform needs to wait for a given period of time before it can confirm an investment or withdrawal.
2. **High Fees:** Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin.
3. **Absence of assets:** Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets on Stellar. An alternative is to get rid of assets and handle only proofs.

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
2. **Need to trust entities providing these applications:** Some DeFi applicaitons are governed by different foundations, and entities on the platform would have to trust these entities to not act maliciously, to not close the smart contract, etc. \(eg. The Maker Foundation in the case of MakerDAO\)

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