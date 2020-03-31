---
description: >-
  This page describes and analyses how the platform functions, and suggests
  suitable alternatives.
---

# Opensolar on Stellar, and alternatives

Recommended previous reading: [https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29](https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29)

## Introduction

Opensolar is a platform for investments in solar energy projects. Opensolar's initial prototype was in Ethereum, and currently uses the Stellar blockchain. In this document, we will explore key advantages and disadvantages of using Stellar, along with other alternative blockchain ecosystems that Opensolar could potentially use.

Opensolar is designed to be modular and each standalone part can be used in a different application. The core opensolar platform is built on top of openx, a broader "platform of platforms" architecture which can be used for a wide range of investment types. Openx provides a base set of JSON-RPC endpoints, a user structure for different users on the platform, optional Know Your Customer \(KYC\) functionality, and other features that are useful for constructing a skeletal platform. Openx platform skeletons can be easily created using the CLI based tool create-openx-app, or can be forked from the main opensolar repository.

Openx's \(and Opensolar's\) architecture is not dependent upon any single blockchain. It is designed to be used with any blockchain as long as there is a contract to interact with a blockchain. Openx right now supports only Stellar but adding support for new blockchains is easy, only requiring the addition of handlers that communicate with other openx fragments. A platform based on Openx has the following parts:

1. A Smart Contract that performs the core functions of the platform 
2. A JSON-RPC interface through which the frontend and other pieces of software can interact with the backend.
3. Auxiliary packages that handle functions like KYC, Stablecoins, different Investment models, etc

The functionality associated with each package within the platform is exposed through a JSON-RPC API. This API follows a token based authentication scheme which callers can invoke.

## Opensolar

Opensolar is a platform built using the Stellar blockchain for investments in solar energy projects. Opensolar enables people to advertise projects in which investors can invest, and the receivers of a project pay the investors back through the course of time.

### Openx

There is one entity on the openx platform that acts as a parent entity for all entities on other platforms - the "User" entity. This entity contains fields that are required for maintaining cross-compatibility with other openx based platforms. It also contains handlers for all cryptocurrencies supported by openx, and platforms are highly recommended to import this functionality from openx. The entity also contains other pieces relevant for a user such as KYC registration and stablecoin support.

As a rule, cryptocurrency operations and handling must take place within the parent openx platform. If platforms would like to add support for other cryptocurrencies, such functionality must be added to the openx repository to enable cross openx platform investments.

Openx uses boltDB, a key value pair database for its internal storage, in order to store user credentials, encrypted user seed, and more.

### Opensolar

Opensolar builds on top of openx and imports the user entity as a parent entity to the entities that it defines. There are different entities on Opensolar such as:

* **Investors**: Investors invest in projects listed on the platform. Investors can vote on projects they like and on changes to be done after their investment is finalised.
* **Recipients / Receivers**: Receivers with the help of originators list projects that need investment on the platform. Receivers are the beneficiaries of projects listed on Opensolar.
* **Originators**: Originators propose projects that might add value to receivers. They work with receivers to prepare a preliminary project plan that contractors can bid on.
* **Contractors**: Contractors bid on projects within opensolar and give a quote to the receiver based on the requirements specified by the receiver and originator.
* **Developers**: Developers install and maintain projects for the receiver. Developers are paid according to the level of support they can give and the amount of time it takes to install a project.
* **Guarantors**: Guarantors provide a failsafe guarantee for investors against receivers who default on payments.
* **Platform Administrators**: Admins review the listings made on the platform and act as arbiters in case of conflict

Investors and Receivers on Opensolar need to perform KYC to be able to invest in and partake in projects listed on Opensolar. Developers and Contractors need to store key details related to their company on the platform to get approval from investors and receivers. Guarantors need to store their details and sufficient proof of funding to act as a guarantor. If entities need to handle Stablecoin \(AnchorUSD\) through the platform, they need to perform KYC on AnchorUSD's website.

Each project has a set of stages and each entity has a specific stage where they are most needed \(for example, investors are needed at stage 4\). Data associated with a stage \("Stage Data"\) must reference associated entities' actions \(in the case of investors, the stage data is on the blockchain\). Stage progression is trigerred by a combination of manual and automatic events, the stage data is stored on IPFS \(Inter Planetary File System\), and the IPFS hash is stored on the platform for future reference.

Opensolar uses boltDB to store opensolar specific details like investor name, receiver name and project details. Once there are more relations between different user entities on Opensolar, a SQL database like postgreSQL is more ideal.

Some data is determined by the appropriate entities \(an example is receivers attesting that the project was installed by taking photos on location\) or by oracles who attest to specific statements \(an example is neighbours atteting that the energy rate charged for the month is the same as the receiver claims it is\). This data is combined with other data associated with the stage and committed to IPFS.

### Stages

An opensolar project is divided into 9 stages ordered chronologically:

Stage 1: **Engagement**  
Stage 2: **Quotes**  
Stage 3: **Signing**  
Stage 4: **Investment**  
Stage 5: **Construction**  
Stage 6: **Interconnection**  
Stage 7: **Legacy**  
Stage 8: **Handoff**  
Stage 9: **End of Life**

Each stage transition is regulated by the smart contract.

### Smart Contract

The opensolar smart contract runs on AWS since Stellar does not support on chain smart contracts. It contains the core functionality surrounding investments and payback whereas auxiliary features that handle transactions like asset creation are imported from sub-packages. The smart contract also allows for different investment models which can be defined in a relevant sub package.

### Stellar

Opensolar's smart contract is designed to use the Stellar blockchain, a Proof of Stake blockchain based on the Stellar Consensus Protocol. Stellar follows an account based model of accounting in which balances are associated with a public key \("account" or "address"\) on the blockchain, and subsequent operations increase the balance associated with the address. Stellar provides a set of operations that can be performed globally to change the state of a set of addresses \([https://www.stellar.org/developers/guides/concepts/list-of-operations.html](https://www.stellar.org/developers/guides/concepts/list-of-operations.html)\). The list of operations used by the Opensolar platform are:

* **Create Account**: To create user accounts on the platform
* **Payment**: To move funds between different accounts on the blockchain
* **Buy Offer**: To exchange XLM with other currencies on the Stellar Decentralised Exchange \(DEX\) \(buy\)
* **Sell Offer**: To exchange XLM and other currencies on the Stellar DEX \(sell\)
* **Set Options**: Used to set thresholds for different signers associated with an account. Used for providing multisig and escrow functionality.
* **Change Trust**: Used to change the trust associated with signers associated with an account. Used for providing multisig and escrow functionality.

The issuance of assets is a feature that is useful to replicate the function of a global state variable \([https://www.stellar.org/developers/guides/concepts/assets.html](https://www.stellar.org/developers/guides/concepts/assets.html)\). Each asset has an issuer, who can issue a limited or unlimited amount of assets \(set by the "Set Options" operation noted above\), and a receiver who trusts the issuer for the specific asset\(s\).

Assets are not trustless, and the receiver trusts the issuer for the asset they receive \(an example is a bank - you trust a bank to not give fake currency when withdrawing cash\). A receiver also specifies a limit called the "Trust Limit", which is the maximum amount of assets they can receive from the issuer \(An example is a friend: you may trust your friend to lend 1000 but not 10000\).

In opensolar, two kinds of assets are used. One is to track the amount owed by a receiver and another to track the amount of pending returns associated with an investor. The Investor asset \("INVAsset"\) denoted by a 12 letter code "INVAssetCode" is 1:1 with the amount they invest in the project \(ie if an investor invests $1000 in the platform, they get 1000 INVAssets\). This ratio scales with the risk and stage of investment \(for example, seed investors may get 1:1.3 for the additional risk they take in providing early capital\)

Receivers receive two assets - "DebtAsset" and "PaybackAsset". The Debt Asset is 1:1 with the net returns associated with a project and each time a payment is made towards a project, DebtAssets are transferred from the receiver to the platform's address. The PaybackAsset is used to track the number of months to full ownership of an installed project. It is also transferred from the receiver to the platform's address with each successfully payment made.

The Opensolar platform has its own account on the blockchain and acts as a pre-escrow for projects listed on the platform. When a project doesn't reach its targeted funding goal or is cancelled, the platform has refunds the investors for the amount invested since it acts as a pre-escrow. The platform can also act as an arbiter if project terms change without prior notification to or without approval of investors, and investors raise a claim with the platform.

The platform also acts as one of the signers of a multi-signature escrow account for projects that have been funded, and each time a receiver needs to withdraw funds \(for example, to pay contractors\), they request approval from the platform. To prevent withdrawal delays, the platform signs all transactions by default. But investors can raise a complaint, and an admin can pause the platform's signing capabilities and arbitrate between investors and recipients.

### Teller

Opensolar uses a piece of software called the "Teller" as an interface between the broader functions of the platform and the installed solar energy grid \(a "solar system"\) on site. The teller keeps track of the energy generated by the solar system and automatically pays the platform back each payment interval depending on the energy generated. The amount to be paid each month is evaluated based on standard tariff charged by energy utilities, and a receiver has the optikon of paying back in bi-weekly or monthly instalments.

The teller also performs auxiliary functions. It tracks the device's location, stores the solar system's state on IPFS in regular intervals, stores the associated IPFS hash on the blockchain at regular intervals, and provides functions for a receiver to view the balance and other data associated with a project locally.

The teller communicates with the platform through JSON-RPC APIs. The receiver is required to store their username and password in a config file stored locally which the teller uses to authenticate with the platform. The teller on first initialization, communicates the location of the device to the platform, assigns and communicates a unique device id generated locally, and for every subsequent restart \(if one occurs\), stores its timestamp.

### AnchorUSD

An entity that wishes to transact in USD must load stablecoin on Stellar through AnchorUSD, a USD based stablecoin provider on the Stellar blockchain. A stablecoin is an asset on Stellar that is 1:1 with the USD \(or other assets, as specified by the issuer\). A stablecoin can be used as a replacement to the dollar on the Stellar blockchain, and can be freely transferred from one address to another like any other asset.

AnchorUSD has a set of rules in place for entities who want to transact in its asset. These rules include KYC and AML verification, along with a registration process listed on anchorusd.com.

Both investors and receivers on Opensolar must purchase USD funds from AnchorUSD. A receiver must purchase USD to payback towards a project and an investor must purchase USD to invest in a project.

Note: AnchorUSD is currently limited to the United States, and as a result, receivers and investor locations are restricted to the United States.

### Investments

The opensolar smart contract can support a variety of investment models and uses a munibond model by default. Other models can be framed as packages and imported into the smart contract.

Investors are required to pass a series of checks before being allowed to invest in projects. These checks include KYC and AML checks \(on the platform, not AnchorUSD\), balance checks, and a ban check to see if the user has been banned on the platform. If an investor fails to meet these criteria, they can not invest in projects on Opensolar.

The platform has two modes - Testnet mode and Mainnet mode. On testnet, the platform simulates a stablecoin called STABLEUSD on the Stellar Development Foundation's Test Network. This stablecoin acts as a replacement for AnchorUSD on testnet to test and simulate stablecoin features. Testnet mode uses test lumens to facilitate payments and enable creation of assets. Test lumens are fetched from the Stellar Development Foundation's Testnet Faucet via the Horizon API.

Opensolar uses the Stellar DEX to enable exchange of assets \(example, XLM for USD\). This DEX can be used to provide functions like secondary asset markets where investors can trade INVAssets for USD or similar.

### Web Interface

The web interface of opensolar is built using React.JS and contains a subset of the functions provided by the opensolar backend. It currently provides user profiles, projects that investors can invest in, and dashboards for recipients, investors and developers.

### RPC API

Opensolar performs all of its interactions with the web interface and teller through JSON-RPC APIs. Some endpoints are public and can be called by everyone without needing a token, and other endpoints are restricted, requiring an account on opensolar and a token to call them.

The token can be fetched by POSTing to `/token` with the username and the 512 byte SHA3 hash of the password. This token is valid for 24 hours but callers can generate a new token even if the timeout interval hasn't been reached.

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

A state in lightning is a cryptographic proof reflecting each peer's balance in a channel. In the event a peer acts maliciously, this proof can be published on Bitcoin-L1, and the malicious peer loses all their funds in the channel.

### LN Hub and Spoke Model

In the Hub and Spoke model, the platform acts as a centralized hub with which all the entities in the platform \(spokes\) interact with. The platform should provide outbound liquidity to all entities, coordinate payments and handle state updates. The platform does not expose public / private keys and handles lightning channels and state updates internally, making the handling of malicious attacks easier because the entities don't have a copy of their state \(only the platform does\). Conversely, this increases responsibility on the platform's end to maintain these states in a stable manner and take frequent updates \(and even possibly hire a watchtower's services\).

When users sign up on the platform, the platform opens an outbound channel with them, providing a fixed amount of liquidity. If users plan on investing in a project when signing, they add funds to the channel either by using Submarine Swaps \(if they possess altcoins\) or splicing funds into the channel.

Submarine swaps is a technique using which users can send altcoin to a specific address and atomically, a tx funding a channel on lightning gets broadcast to the Bitcoin blockchain. Splicing funds into a channel is done by closing a channel, adding an extra input and opening a channel in the same transaction. There are other means of funding a channelm and any can be used as long as the investor manages to successfully create a channel with the platform.

An alternate way is to not have a channel unless an investor wants to invest and the investor can create the channel when they want to invest. The downside to this approach is that investors have to wait for the transaction to be reliably confirmed before the platform can confirm their investment An investor creating a channel or pushing funds to the platform would have to push some amount extra to cover for the on chain fees of creating a channel. The project's total desired funding amount should have a small buffer for funding lightning channel openings/closings to make these free for the entities involved.

For other entities, the platform opens a channel if and once the project they are associated with is funded. This prevents the need of dealing with channels that aren't being used. The platform should close channels by default if they haven't been used in the past 3/6 months in order to efficiently manage liquidity, and to minimise attack vectors surrounding liquidity. If a project's expected time to funding is greater than this period, the channel should be kept open until the project's expected time to funding elapses.

Once a channel is in place, the investor pushes the amount they wish to invest towards the platform. When the investment amount reaches the project threshold, the platform opens a new outbound channel with the receiver, developer and other entities, the project is marked complete, and the investor is given the transaction ids of the channels that the platform newly opened, and pushes back a small amount back towards the investor \(the platform updates the last known state, and now that the investment is one state deep\).

The investor could choose to transfer some small amount funds back to the platform through additional investment or through donations in order to bury the bigger investment within the list of states, and increase the effort required by a malicious platform admin to defraud them. The investor could also close the channel but closing and opening a new channel each time an investment is completed or initiated has no difference compared to a Bitcoin-L1 transaction. There is scope for improvement where we have the ability to detect user behaviour and recommend on-chain funding if the fee is low or if they do not plan on investing in more than one project.

With the newly established outbound channel, the platform and the receiver have to collaborate to send funds to different entities \(the platform should cooperate by default\). If the receiver wishes to pay the developer, it tells the platform that it wants to push funds to the developer and the platform will push funds through its channel with the developer. Alternatively, the platform can push funds towards the recipient and the recipient can choose to route funds either through the platform or other means to the developer \(the receiver could also receive LN payments from the platform and pay the developer off chain\). Guarantors need to open a channel with the platform \(or top up the balance on their end towards the platform\) and in the event of the receiver failing to pay, the guarantor should push funds towards the platform and the platform will treat this as a normal payment from the receiver \(while keeping note and sending notifications to all parties on the platform\).

The receiver could also provide an invoice which the investor funds through a non-openx account if they wish to do so. The platform could still be able to pay the investor for their investment since it can scan the pubkey of the investor from the blockchain. This also enables donation projects where investors are looking to donate funds to different projects through the Bitcoin Lightning Network.

Investors holding altcoins could use atomic swap services \(which could either be facilitated by the platform or by a third party service\) or submarine swaps to invest in projects as described earlier.

The platform should take note of griefing attacks \(ie\) when users sign up as receivers or developers but don't use the account, effectively forcing the platform to lock funds for the period of time defined. This can be avoided by only opening channels with entities that are already associated with a project, and by efficiently closing unused channels.

The trust model in this scenario is that entities trust the platform \(to push funds to the developer, contractor, create multisig escrows, etc\). The availability of proofs in the form of state update hashes and tx ids removes the need for state variables.

### Advantages

1. More Decentralised: It is easy for people to run a lightning node since it doesn't require a lot of resources. Even if people don't run their own nodes, node outreach and communication can be made private with technology like Neutrino.
2. Faster payments: Since Lightning transactions are settled immediately, this is faster than having to wait for a block like in the case of Stellar
3. Easy API and partner integration: A varied group of partners are available in the Lightning ecosystem and it is easy to leverage their help to improve the functionality of Opensolar. Building on Lightning would also enable the possibility of lightning mobile apps - web platform integration, which would make it easy for receivers to pay back towards specific projects.
4. Good Functionality: Lightning offers more functionality \(atomic swaps, state update proofs\) that Opensolar could expand on compared to Stellar, and Lightning core development is faster than Stellar.
5. Option to switch between Bitcoin-L1 and Lightning: Bitcoin is the most liquid asset and there are lots of people building on top of Bitcoin.

### Disadvantages

1. Need to manage liquidity: Since the platform acts as a central provider of liquidity, it should maintain a non trivial balance of Bitcoin to open and close channels, and should manage these balances efficiently. Failure to manage balances could lead to the platform's inability to open new transactions and therefore, increase costs. Maintaining these balances also means there's an amount that belongs to the platform that is always locked and not spendable. As the platform grows in the number of projects, this may be an issue.
2. Need to handle channel closing: Since lightning works on a channel based infrastructure, the platform should be adequately equipped to handle channel closures \(both by the platform, and by the entities on the platform\). An alternative might be that the platform does not offer channel closures to entities on the platform though this comes at the cost of reduced decentralisation.
3. Handling large payments: Lightning is still in its infancy with respect to channel capacity and large amounts that need to be transferred sometimes fail to find a route. One way to handle this is by ramping up channel capacity on the platform's end as needed although this woulc conflict with 1 above, and make liquidity handling more difficult.

### Pre-signed Transactions Model

A transaction in bitcoin requires signature from all private keys associated with the input utxos. A signed transaction can be broadcast to the blockchain anytime provided the spending conditions are still valid at the time of broadcast. A transaction that is signed and not broadcast can be stored as a pre-signed transaction and broadcast whenever required. This transaction can also have conditions associated to spending \(for example, invest 1000 in this project within 3 months, else refund money to this other address\) that refund to a user if not broadcast within a certain interval of time.

If an investor wishes to invest in a project, they could give a pre-signed transaction to the platform guaranteeing their investment if it reaches a certain threshold within some point in time \(defined by the investor or set to default by the platform\). If the investment threshold is reached, the platform checks the blockchain and if the utxos aren't spent elsewhere, broadcasts the transaction. The investor can also add conditions to investments which are a combination of project conditions, and blockchain rules \(example: if this project raises atleast 10000 within 1 month, invest 4000 else wait for project investment and refund after 3 months if project threshold is not reached\).

Similarly the platform on completion of investment, signs transactions paying funds to the developer and contractor but does not publish them until the receiver has marked their role complete. The guarantor gives pre-signed transactions that the platform agrees to not publish unless the receiver defaults on a number of payments.

In the event that the investment threshold is not reached, the investor should spend the funds associated with the address to another address or specify a refund address as a condition in the pre-signed tx. The latter places responsibility for broadcasting the transaction onto the platform and the former places emphasis on the investor to transfer their funds as soon as their time for investment has expired. Pre-signed transactions can be made blind with the addition of Schnorr Signatures to the bitcoin protocol.

This model would involve the construction of a secure way to store these transactions since any user in possession of them can broadcast the transaction. We could also attach one time passcodes that are relayed on the completion of certain events to encrypt the transactions and therefore prevent this problem from occurring.

The trust model of this idea relies on the platform not grief attacking its users and not broadcasting funds. At most, the platform has the ability to selectively censor txs, prevent recipients from getting money, etc.

### Advantages

1. Easy proof handling: Giving an entity proof of a transaction is as simple as giving the hash of the pre-signed transaction id. When the transaction is broadcast, the entity can see the transaction on the blockchain, take the hash and compare it with what they had.
2. Security and Decentralisation of Bitcoin-L1: Due to Bitcoin's high PoW, a pre-signed transaction that is broadcast can almost never be reversed if the receiving entity waits for a given period of time.
3. Easy to refund investors: Investors can either choose their own criteria for refunds, or the platform can simply delete the pre-signed transaction in the event the investment threshold is not reached, or if there is a problem with the project.
4. Big partner ecosystem: Bitcoin has a lot of partner companies which are looking to improve different aspects of using and getting on to Bitcoin.
5. More functionality: Bitcoin has more opcodes than Stellar, and can therefore the platform can look to implement more complex functionality.

### Disadvantages

1. Less decentralised than Lightning: Since the platform possesses a list of pre-signed transactions, a malicious entity could make the platform not broadcast these, thereby griefing the entities involved in the transaction. Although such an attack would come at a reputational risk to the platform, this places more requirements on the platform than Lightning.
2. Absence of assets: Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets in Stellar. Bitcoin does have a number of alternatives but they haven't grained traction or adoption, so we would have to come up with a new solution. An alternative is to get rid of assets altogether and handle only proofs.
3. Slow confirmation times: Bitcoin transactions are slower than comparable Stellar transactions, so the platform can not afford to make a lot of synchronous payment requests during the investment workflow.
4. High Fees: Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin.

### Sidechains

Sidechains are similar in design to the Lightning Network in that they act as a parallel layer for settlement of transactions. They differ in construction in that they don't have channels, liquidity or other things that LN possesses. Instead, their design is the same as Bitcoin-L1 except that the block headers are committed at regular intervals to Bitcoin-L1, or their blocks merge-mined along with Bitcoin-L1 with smaller commitments being made on the sidechain. A sidechain when viewed from the outside looks no different than a standard blockchain.

A sidechain can provide an improved set of features \(eg: the block interval can be smaller\). There might not even be fees associated with these blocks depending on the conditions set in the sidechain. All bitcoin protocol rules valid in Bitcoin-L1 are valid in a sidechain based on Bitcoin, although a sidechain can be based off a different currency like Ethereum and commit only state updates to Bitcoin-L1.

Each openx platform can be on a sidechain and a centralized coordinator can group the hashes and commit them at regular intervals. Functions inside the platform can be same as that on Bitcoin except they can be faster, cheaper and have more features added on to the base layer. Each individual platform need not worry about whether it is running on a sidechain or not since there is no difference.

An alternate architecture would be one where each platform submits transactions and other changes to the bigger openx platform, and openx decides which sidechain to post the transaction to. Additional features \(that are not present on the Bitcoin base layer\) if used can be marked with flags. Openx maintains an internal store of the transactions requested by a platform. Openx can also broadcast transactions without flags to Bitcoin-L1 if fees are low. In this architecture, openx should return a proof to the caller platform \(ideally a tx id\) that the transaction was broadcast, along with a sidechain identifier. This identifier can be used on a sidechain explorer \(which should be run by openx\) to identify the transaction.

The sidechain explorer should contain the details of the tx \(like a normal blockchain explorer\) along with the L-1 block the chain's headers were committed to. This way, entities in possession of the proofs can easily cross reference where their transactions were committed.

A sidechain could also be used in combination with another Bitcoin-L1 or another blockchain. The sidechain could be used as a layer for updating state and Bitcoin-L1 could be the layer where investments and payments happen.

The trust model for this depends on the sidechain's construction - who can create blocks, who can post transactions, etc. Since opensolar's idea revolves around trusting the platform, the platform can be the entity that performs these functions. Existing sidechains like Liquid or merge mined coins like RSK can also be used in place of a custom sidechain. The change is that one should trust the entities controlling these sidechains along with the platform itself.

### Advantages

1. More Functionality: Sidechains offer a wide range of functionality like smart contracts, asset and confidential transactions which can be used to improve platform functionality.
2. Fast transactions: Sidechains are usually faster than Bitcoin-L1.
3. Easy integration with Bitcoin-L1 and Lightning: Sidechain pegs are easy and usually all a person has to do is send Bitcoin to a specific sidechain address in order to enter the sidechain. Onboarding is therefore easier since one can leverage the partner ecosystem of Bitcoin.
4. More decentralised than Stellar: Sidechains usually have more running nodes than Stellar and therefore, it is less likely a transaction will be censored.
5. Low fees: Sidechains usually have negligible fees as compared to Bitcoin-L1.

### Disadvantages

1. Need to depend on the sidechain's consensus mechanism: The sidechain may have its own consensus mechanism and scheme, and this is usualyl worse than Bitcoin-L1.
2. Deposits and Withdrawal delays on the sidechain: When an entity wants to withdraw funds, they need to wait for the next commitment / merge mined block on Bitcoin, and subsequent confirmations on Bitcoin in order to withdraw their funds.
3. Not time tested: Sidechains are relatively new, and their security has not been as time tested as Bitcoin.

### Statechains

Statechains is an improvement on top of Sidechains which combines the Hub and Spoke model of LN with the semi trusted nature of Sidechains. Statechains requires a centralized coordinator which communicates with the others in the system, and stores an index mapping utxos to owners. Statechains as is can enable transfer of whole utxos \(without breaking\) from one entity to another with zero cost.

Each person who wants to enter the statechain can do so by creating a 2/2 Multisig address with the coordinator "C". If "A" would like to transfer to "B" an utxo "X", it passes the private key "x" to B through C \(which checks if A is indeed the owner of X, adds its signature and broadcasts it to the blockchain\), which updates its index that B is the owner of the marked utxo. A is required to delete the private key from its storage. Even if A maliciously stores the private key and attempts to spend it elsewhere, C refuses to sign because its record shows that A transferred ownership of X to B.

In the case of opensolar, the above is not an issue since utxos are never exposed to the user. The platform could act as a centralised coordinator and investors can transfer utxos to the platform conditional on the investment threshold being reached. In the event the threshold is not reached, the utxo's ownership will not change. Once the investment threshold is reached, the utxos are transferred to an intermediary, and spending from the intermediary requires the approval of both the platform and the receiver. When the receiver wants to pay certain entities, it requests the platform to sign the transaction, and the platform transfers ownership of the utxo to the other entity.

Statechains can also support multiple currencies \(that follow an utxo model\), and users can choose to swap currencies within the statechain. This also gives flexibility to the receiver, who can pay entities in other currencies if the entity chooses so. Note that this requires Schnorr signatures as a minimum upgrade to the Bitcoin protocol. Statechains can also be used in combination with payment channels, and people can use these utxos to fund a channel between two peers.

The trust model for this idea again relies primarily on the platform not acting maliciously, or in collusion with one of the previous owners of the utxo. In the event this occurs however, proofs of ownership are easy to publish, and the platform's reputation will be ruined.

### Advantages

1. Improved privacy: Statechains have improved privacy compared to pre-signed transactions since the platform signs every transaction change request. This interaction between entities and the platform can be made more private with Schnorr signatures.
2. Support for altcoins: Statechain coordinators can offer support for altcoins, enabling easy exchange of altcoins, stablecoins and Bitcoin within the platform.
3. Security and Partner Ecosystem of Bitcoin-L1: Statechains is an architectural expansion of Bitcoin-L1, and offers the complete security guarantees of Bitcoin-L1.
4. No fees: There are no fees associated with the transfer of utxos within a statechain.
5. Fast transactions: Transactions are almost instant on the statechain since there is no blockchain confirmation period involved.

### Disadvantages

1. Less decentralised than Lightning: Since the platform acts a a central coordinator for processing statechains, any of the previous owners of the utxo could collude with the platform in order to steal funds from the user. Such an attack will be public and comes at a reputational cost to the platform but still is more centralised than Lightning which doesn't place any such requirements.
2. Absence of assets: Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets in Stellar. Bitcoin does have a number of alternatives but they haven't grained traction or adoption, so we would have to come up with a new solution. An alternative is to get rid of assets altogether and handle only proofs.
3. Slow confirmation times: Bitcoin transactions are slower than comparable Stellar transactions, so the platform can not afford to make a lot of synchronous payment requests during the investment workflow.
4. High Fees and whole utxos: Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin. Statechains also require complete utxos and splitting utxos should occur as a transaction on Bitcoin-L1.
5. Not time tested: Statechains is a recent development, and hasn;t been battle tested for flaws

### Bitcoin L-1

Similar to how things work on Stellar, the same transactions could be mirrored on Bitcoin.

### Advantages

1. Best security and decentralisation: Due to Bitcoin's PoW consensus model, it is extremely expensive for an attacker to attempt to censor or rewrite transactions. Bitcoin also has a large number of nodes \(&gt;10000\) which greatly improves decentralization.
2. Big partner ecosystem: Bitcoin has a lot of partner companies which are looking to improve different aspects of using and getting on to Bitcoin.
3. More functionality: Bitcoin has more opcodes than Stellar, and can therefore the platform can look to implement more complex functionality.
4. Best Liquidity: Bitcoin is the most traded cryptocurrency asset, and liquidity on markets is not a problem.
5. On chain verification: Bitcoin Script is verified on chain, and the platform need not be trusted for performing computation correctly.

### Disadvantages

1. Slow confirmation times: Bitcoin transactions are slower than comparable Stellar transactions, so the platform can not afford to make a lot of synchronous payment requests during the investment workflow.
2. High Fees: Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin.
3. Absence of assets: Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets in Stellar. Bitcoin does have a number of alternatives but they haven't grained traction or adoption, so we would have to come up with a new solution.

## Ethereum

Ethereum uses an account based model, similar to Stellar. Changing to this model would involve major changes since Ethereum provides a Turing complete on chain smart contract abstraction \(called the Ethereum Virtual Machine or EVM\) which eliminates the need for assets, and global state variables. This would also mean the opensolar smart contract which runs on a server right now could migrate to the Ethereum blockchain.

Ethereum provides a wide range of opcodes to work with, and functionality can be expanded arbitrarily. Ethereum charges a fixed "gas" for each common operation \(hashing, adding, multiplying, state updates, etc\) and a variable amount of gas for other operations. Transaction fee is denominated in gas, and the more operations a state update contains, the more gas it consumes. Gas and ETH are subject to their own fee markets.

The EVM is a powerful abstraction for developers who want to run smart contracts on chain. Running these contracts on chain provides provable execution without having to provide proofs in between each computation. An on chain smart contract improves auditability of the contract, and one can easily check if the code on the repository is the same as the code deployed. This enables third party monitors to monitor updates / investments on the platform and alert users in case something fishy happens, and also for third party services to create their own web interfaces for Opensolar.

Ethereum has a large developer ecosystem and lots of potential ideas and applications that can be used without much effort. These use cases can potentially augment the primary use case of the platform and enable the intersection of many ideas.

Ethereum has L2 solutions similar to Bitcoin \(eg. Plasma\). Ethereum is transitioning to a Proof of Stake system where miners stake ETH in the system instead of hashing. Ethereum also has provisions to incentivize developers to work on projects through decentralized crowdfunding ideas \(example Gitcoin\). This could be a mechanism to fund development on opensolar, and fund hackathons / bounty programs.

### Sharding

Sharding is a distributed systems concept where a single piece is split into multiple pieces and consistency of data is managed by an algorithm communicating with the different pieces. Splitting data reduces data storage requirements, increases local read/write speed, and efficiency of individual shards. Each shard ultimately communicates with the other shards either during a fixed time interval \(eg: once in 30 minutes\) or through a protocol.

In the context of Ethereum, Ethereum has a big archival storage requirement due to the requirement to store previous state updates of all deployed and inactive contracts. Sharding Ethereum's storage into multiple parts improves performance of local shards, and provides faster transaction confirmation. It also enables each shard to have its own set of rules locally, and these changes need not be reflected or stored on the parent Ethereum blockchain.

In the context of opensolar, we could use a two layer shard system where each platform could live on its own shard with its own set of rules, and communicate with a bigger openx shard which commits to Ethereum blockchain. State updates can be fast, local and free, and different proofs can be given to different entities \(once the platform once the parent openx shard commits to the Ethereum blockchain, shard chain header, etc\).

Like sidechains in Bitcoin, this requires a shard explorer in order to navigate through the different shards present in the system in order to find a given update. The shard explorer would contain normal details of a transaction or state update along with the block in which the openx shard committed the particular change.

Shards need not necessarily be Ethereum based, they could also be different blockchains whose headers commit to the parent openx shard. Some platforms may have an increased amount of trust placed in them, and they could choose to commit certain state changes to the shard living above them.

The trust model for this involves trusting the openx shard and the platform shard. If a shard owner tries to cheat any given entity, they have proofs that they can show to ruin the platform's reputation.

### Advantages

1. Low Fees: Each shard can process transactions faster and more cheaper \(since the shards communicate with each other only at certain intervals\)
2. Big partner ecosystem: Ethereum has a lot of partner companies which are looking to improve different aspects of using and getting on to Ethereum.
3. More secure and decentralised than Stellar: Shards are easy to run, and the requirement to become a shard validator is not too high. The number of nodes running Ethereum full nodes is around 6000 and the number of shards will only be more, making it more decentralised than Stellar.
4. More functionality: Since shards replicate the functionality of Ethereum-L1, the EVM and other features are available for the platform to use.
5. Faster transactions compared to Ethereum-L1: Transaction processing is split into multiple shards and each shard can process the same amount of transactions faster \(since there are more processing units to process them\).

### Disadvantages

1. Not time tested: Sharding is not a new idea but implementations of sharding in the blockchain space have not been tested.
2. Need to handle shard commitments, updates and malicious behaviour: There is a possibility that a participant in the platform coordinates with shard validators to defraud the platform \(or the platform can coordinate with validators to defraud entities\). These scenarios need to be handled varefully within the platform.
3. Compatibility with Beacon Chain unclear: It is unclear how compatible Sharding will be with the Ethereum PoS upgrade.

### DeFi and algorithmic stablecoins

DeFi or decentralized finance is a new development which seeks to replicate existing financial technology use cases on top of Ethereum. Common examples are loans, lending, stablecoins, arbitrage, etc \(product examples are: sDAI, mDAI, Gitcoin, Liquidity protocol, Uniswap\).

A potential usecase is chaining together some of these applications and using the combination to invest on projects in the platform. As an example, an investor can use their ETH as collateral to obtain a USD loan to invest in the platform's projects. A recipient could advertise projects that deposit real world collateral in exchange for short-medium term loans for investments in their projects. Entities can also have their project listed as a Gitcoin proposal and ask for funding from the community, and investors can receive returns through the platform.

This model would have to be supplemented by a base layer blockchain which handles the non payment part of the infrastructure. This could be Ethereum-L1 or other blockchains and openx would need to support various Ethereum operations in order to be compatible.

The trust model for this depends on the chain of applications \(for DAI, you trust the algorithm to keep the peg, for Gitcoin you assume there are no bots trying to game the system\).

### Advantages

1. Easy onboarding and big partner ecosystem: DeFi applications are available in a variety of countries and local onboarding might be easier.
2. More financial functionality: Since there is more scope for moving assets around, there can be improvements on the financial side of the platform.

### Disadvantages

1. Hacks: Many DeFi applications are unaudited and as a result, are prone to hacks.
2. Need to trust entities providing these applications: The Maker Foundation in the case of MakerDAO, different teams working on the smart contracts, etc.

### Decentralised Autonomous Organisations

A DAO is an organisation in which the participants have a say on decisions made by the DAO depending on the amount they have staked / invested in it. This enables decentralised applications of centralised systems like voting, community participation, etc with anonymity .

A DAO could be used by entities to vote on project timelines, to vote on whether they are satisfied with the project's deployment, what projects to list on the platform, and more. It could also be used when deciding on the timeline of the platform's development, who's responsible for developing the platform, etc.

This model would have to be supplemented by a base layer blockchain which handles the non governance part of the infrastructure. The base layer should be Ethereum-L1 since only then can people vote or stake on proposals with ETH.

The trust model is that one trusts the DAO \(the algorithm the DAO is based on\) to take actions based on the majority of votes cast for or against a proposal.

### Advantages

1. More decentralised than Ethereum-L1: The barrier of entry to a DAO is low and as a result, people can easily participate in DAOs.
2. More participation functionality: The platform could run its own DAO instance and by making the barrier to entry low or free, could invite community members to participate in governance.

### Disadvantages

1. Hacks: Like the famous case of TheDAO, DAOs are a double edged sowrd and must be relied on with caution.
2. Over-application: In some cases, having a DAO slows the decision making process.

### Bridges

Ethereum offers bridges to other cryptocurrencies like Bitcoin. These bridges could be used to construct a dual layer commitment system where proofs exist in two blockchains, choices between two chains depending on the fee, atomic swaps with other chains using the smart contract, etc.

A bridge in essence is having two-L1 blockchains to commit to, and the trust model is dependent on the least secure of the two blockchains, along with the bridge's smart contract.

### Advantages

1. The advantages of bridges is a combination of the blockchain systems it is based on.

### Disadvantages

1. Need to trust entities providing the bridge, and the smart contracts powering the bridge.

### Layer 1 Ethereum

Ethereum's EVM offers a powerful on chain smart contracting interface. This can be used to offer verifiable contract execution on chain, global state variables, etc.

The platform's contract could be deployed on chain and investors, receivers, etc would interact with the contract through standard tools available on Ethereum. Investment proofs, state variables are all stored on chain so there is minimal requirement for an in house database that serves these functions \(as is right now\).

Ethereum-L1 can also be used in parallel to another blockchain system. For example, payments can take place on Bitcoin, and state updates and storage can take place via Ethereum. This gives the dual benefit of low fees while still having auditable smart contracts on chain. This case is a slight twist to the bridge scenario described earlier.

### Advantages

1. Better security and decentralisation: Due to Ethereum's PoW consensus model, it is extremely expensive for an attacker to attempt to censor or rewrite transactions.
2. Big partner ecosystem: Ethereum has a lot of partner companies which are looking to improve different aspects of using and getting on to Ethereum.
3. More functionality: Ethereum's EVM provides the ability to replicate any program on Ethereum
4. Good Liquidity: Ethereum is the second most traded cryptocurrency asset, and liquidity on markets is not a problem.
5. On chain verification: The EVM provides an easy mechanism to verify computation on chain.

### Disadvantages

1. High Gas and Transaction Fees: Ethereum transaction fees depend on the gas market, which fluctuates depending on the usage of Ethereum.
2. High Complexity: Due to the EVM's complexity, there are multiple avenues for unexpected results, hence a thorough audit is required.
3. Uncertainty due to Proof of Stake shift: Since Ethereum is shifting to a PoS system in the near future, it is unclear if all the functionality of Ethereum-L1 will be preserved in the new chain.

## Cosmos

Cosmos is a proof of stake blockchain with an aim to be the "blockchain of blockchains" by enabling connections to multiple other blockchains. Cosmos' modular architecture enables multiple openx platforms to communicate with each other by connecting to different nodes that offer services on Cosmos.

## Hyperledger

Hyperledger is an open sourced permission blockchain system. Hyperledger's permission model allows only certain nodes to run, and these nodes are held accountable. Hyperledger has two main implementations - Hyperledger Fabric and Hyperledger Indie.

## Polkadot

Polkadot is a spin-off from Ethereum's original Web3.0 ideas. Polkadot, similar to Cosmos, wants to enable bridges to other cryptocurrencies and serve as a connecting layer for blockchains.

