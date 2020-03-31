---
description: >-
  This page describes and analyses how the platform functions, and suggests
  suitable alternatives.
---

# Opensolar on Stellar, and alternatives

Recommended previous reading: [https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29](https://gist.github.com/Varunram/b8c0da7b9d553fb0be233be1f99b0d29)

## Introduction

Opensolar is a platform for investments in solar energy projects. Opensolar's initial prototype was in Ethereum, and is built on the Stellar blockchain. Through working with Stellar over the course of the past year, we have come to identify key advantages and disadvantages to using Stellar. In this document, we will explore these, along with other alternative technologies that Opensolar could potentially migrate to.

Opensolar is designed to be modular, with different parts intended to be used in other systems. The core opensolar platform is built on top of openx, a broader "platform of platforms" architecture which can be used for a wide range of investments. Openx provides a base set of JSON-RPC endpoints, a user structure for different users on the platform, optional Know Your Customer \(KYC\) functionality, and other features that are useful for constructing a skeletal platform. Openx platform skeletons can be easily created using the CLI based tool create-openx-app, or can be forked from the main opensolar repository.

Openx's \(and Opensolar's\) architecture is not dependent upon any single blockchain. It is designed to be used with any blockchain as long as there is a contract to interact with and retrieve data from the blockchain. Openx right now supports only Stellar, but adding support for new blockchains is as easy as adding the required handlers. A platform based on Openx has the following parts:

1. A Smart Contract for performing the core functions of the platform 
2. A JSON-RPC interface through which the frontend \(and other pieces of software like the "teller"\) can interact with the backend.
3. Auxiliary packages for handling functions like KYC, Stablecoins, different Investment models, etc

The functionality associated with each modular package is exposed through a JSON-RPC API which follows a token based authentication scheme which callers can invoke.

## Opensolar

Opensolar is a platform built on top of the Stellar blockchain for investments in solar energy projects. Opensolar advertises projects of a specific capacity in which investors can invest, and the receivers of a specific project pay back the investors in a specific period of time.

### Entities

### Openx

There is one kind of entity on the openx platform that is to be used by all platforms importing openx: The User entity. The user entity contains commonly used fieds that are needed for maintaining compatibility with openx. The entity also contains handlers for all cryptocurrencies supported by openx, and it is highly recommended for platforms to import this functionality from openx and not deal with handling cryptocurrencies by themselves \(because openx's code is easier to audit, follows code standards, etc.\). Openx also contains other pieces relevant for a user entity such as KYC registration, stablecoin support, etc. However, as a rule, cryptocurrency operations and handling must take place within the openx package \(if platforms would like to add support for other cryptocurrencies, they are requested to make a Pull Request to the openx repository\)

### Opensolar

Opensolar builds on top of openx, so it imports the user entity within the entities that it defines on the platform. There are different entities on Opensolar playing different roles on the platform:

* Investors: Investors invest in projects listed on the platform
* Recipients / Receivers: Receivers with the help of originators list projects that need investment on the platform
* Originators: Originators propose projects that might be useful to receivers
* Contractors: Contractors give a quote to the receiver based on the requirements specified by the receiver and originator
* Developers: Developers install services for the receiver
* Guarantors: Guarantors provide a failsafe for receivers who might default on payments.

Apart from these, there are platform administrators who review the listings made on the platform, and who act as arbiters in case of conflict between a set of investors and receivers.

Investors on Opensolar would need to pass KYC regulations in order to invest in projects. Receivers go through a similar check in order to ensure that the project they are requesting funding for is legitimate. Developers, Contractors, etc. need to store key details related to their company on the platform, in order to get approval from investors. If they choose to handle Stablecoin via the platform, they must pass KYC regulations as required by the stablecoin provider.

Each project has stages through which it progresses and each entity has a specific stage where they are most needed \(for example, investors are needed at stage 4\) and the stage data associated with this stage must reference their actions \(in the case of investors, the stage data is on the blockchain\). Stage progression is trigerred by a combination of manual and automatic events, and the documents in stage data are stored on IPFS \(Inter Planetary File System\).

Other storage requirements on Opensolar like Investor details that don't need to be proven to others are stored in a boltDB, a key-value pair database. In the future, once Opensolar expands to have more entities and relations, we could move to a SQL based database like postgreSQL.

### Stages

An opensolar project is divided into 9 stages ordered chronologically and numerically:

Stage 1: Engagement  
Stage 2: Quotes  
Stage 3: Signing  
Stage 4: Investment  
Stage 5: Construction  
Stage 6: Interconnection  
Stage 7: Legacy  
Stage 8: Handoff  
Stage 9: End of Life

Each stage has a set of criteria \("Stage Data"\) that is required to be fulfilled before proceeding to the next, and this is defined in the smart contract. Some data like "Is the project installed at the location?" is determined by the appropriate entities \(Receivers, for the above example\) and they can take photos, have someone attest that the project was installed at the location, etc.

### Smart Contract

The opensolar smart contract runs on AWS due to Stellar's inavailability of on chain smart contracts. The smart contract contains the core functionality surrounding investments, payback whereas auxiliary features that handle transactions, asset creation are imported from sub-packages.

### Stellar

Opensolar's smart contract is designed to use the Stellar blockchain, a Proof of Stake blockchain \(based on the Stellar Consensus Protocol\) designed for fast settlements. Stellar follows an account based model in which balances are associated with a single public key \("account" or "address"\) on the blockchain, and subsequent operations increase the counter associated with an address. Stellar provides a small set of operations that can be performed globally to change the state of a set of addresses \([https://www.stellar.org/developers/guides/concepts/list-of-operations.html](https://www.stellar.org/developers/guides/concepts/list-of-operations.html)\). The list of operations used by the Opensolar platform are:

* Create Account: To create user accounts on the platform
* Payment: To move funds between different accounts on the blockchain
* Buy Offer: To exchange XLM with other currencies on the Stellar Decentralised Exchange \(DEX\) \(buy\)
* Sell Offer: To exchange XLM and other currencies on the Stellar DEX \(sell\)
* Set Options: Used to set thresholds for different signers associated with an account. Used for providing multisig and escrow functionality.
* Change Trust: Used to change the trust associated with signers associated with an account. Used for providing multisig and escrow functionality.

A primary feature of Stellar that is useful for replicating the function of a global state variable is the issuance of Assets \([https://www.stellar.org/developers/guides/concepts/assets.html](https://www.stellar.org/developers/guides/concepts/assets.html)\). Each asset has an issuer, who has the authority to issue a limited or unlimited amount of assets, and a receiver, who needs to trust the issuer to issue the specific assets. Assets are not trustless, and the receiver trusts the issuer for the asset they receive \(a common example is a bank - you trust a bank to not give fake currency when withdrawing funds\). A receiver also specifies a limit called the "Trust Limit", which is the amount upto which they trust the issuer to receive the asset in question \(You may trust your friend to lend 1000 but not 10000\).

On opensolar, two assets are used to track the amount owed by the receiver and one asset used to track the amount of expected returns associated with an investor. The Investor asset \("INVAsset"\) denoted by a 12 letter code "INVAssetCode" is 1:1 with the amount they invest in the project \(ie if an investor invests $1000 in the platform, they get 1000 INVAssets\). This ratio scales with the risk and stage of investments \(for example, seed investors may get 1:1.3 for the additional risk they take in providing early capital\)

Receivers receive two types of assets - "DebtAsset" and "PaybackAsset". The Debt Asset is 1:1 with the total returns associated with the project, and each time a payment is made towards the borrowed capital, DebtAsset is transferred from the receiver to the platform's account. The PaybackAsset is used to track the months left to complete ownership of the installation \(in the case of a solar project, a "solar system"\). This PaybackAsset is updated with each successfully payment made toward borrowed capital.

The Opensolar platform also has its own account on the blockchain, and acts as a pre-escrow for projects listed on the platform. This means that if a project doesn't hit its targeted funding goal or is cancelled due to other reasons, the platform refunds the investors for the amount invested. This pre-escrow functionality can also act as an arbiter in case project terms change in the future without prior notification to or without approval of investors. The platform also acts as one of the signers of a multi-signature escrow account for projects that have been funded, and each time a receiver needs to withdraw funds \(for example, to pay contractors\), they need to get approval from the platform to do so. To prevent delays in withdrawals, the platform signs on all transactions by default but investors can raise a complaint and an admin can change this to arbitrate between the investors and recipients.

### Teller

The solar installation used a piece of software called the "Teller" to interface with the broader functions of the platform. The teller keeps track of how much energy is being generated by the system and generates a bill amount equivalent to the energy produced which the receiver pays back in bi-weekly or monthly payments. The teller also tracks the device's location, provides functions to view the balance associated with a receiver's address, and other augmented functions that can be used to query the status of the teller.

The teller communicates with the platform through RPC APIs. The receiver is required to put in their username and password in a config file stored locally, which the teller uses to authenticate with the platform. The teller on first initialization, passes the location of the device and assigns a unique device id to itself, and for every subsequent restart \(if one occurs\), stores the time of the restart. The teller also commits energy production data to ipfs locally, and this storage state is committed at regular intervals to the Stellar blockchain.

### AnchorUSD

An investor on opensolar must load stablecoin using AnchorUSD, a USD equivalent provider on the Stellar blockchain. This process is external to the system, and a user is required to go through the AnchorUSD workflow before they can deal with payouts or investments on the platform. A receiver must load AnchorUSD funds on their account before they attempt to pay monthly bills. A receiver's account is automatically debited during each payment cycle and they are sent notifications in the event their balance is less than the monthly bill.

AnchorUSD is currently limited to the United States, and as a result, receivers and investors are restricted to being in the United States.

### Investments

The opensolar smart contract can support a variety of investment models and uses a munibond model by default. Other models can be added in a modular way and plugged into the parent contract for it to use.

Investors are required to pass a series of checks before being allowed to invest in the system. These checks include KYC and AML checks, balance checks, and a ban check \(if the user has been banned on the platform\). Depending on the platform's need, these can be expanded to include more checks.

The platform is divided into two modes - Testnet and Mainnet. On testnet, the platform simulates a stablecoin called STABLEUSD on the Stellar Development Foundation's Test Network. This stablecoin acts as a bootstrap in place of AnchorUSD \(on mainnet\) in order to test and simulate stablecoin functions. Testnet also uses test lumens to facilitate payments and enable creation of assets. The asset codes on testnet and mainnet however, are the same.

Opensolar also uses the Stellar DEX to enable easy exchange of assets \(example, XLM for USD\). This DEX can be used to provide functions like secondary asset markets where investors can trade INVAssets for USD or similar.

### Web Interface

The web interface of opensolar is built using React.JS and contains a subset of the functions provided by the opensolar backend. It provides a set of projects that investor can invest in, and allows recipients to login and see their project status, and energy generation.

### RPC API

Opensolar performs all of its interactions with the web interface and teller through JSON-RPC APIs. Some endpoints are public and can be called by everyone without needing a token, and other endpoints are restricted, requiring an account on opensolar, and a token to call them.

The token can be fetched by POSTing to `/token` with the username and the 512 byte SHA3 hash of the password. This token is valid for a day but callers can ask for a new token even if the timeout interval hasn't been reached.

## Advantages of Stellar

Stellar has the following advantages for opensolar:

1. **Fast and cheap payments:** Stellar transactions are confirmed within 5s and the transaction cost is very low \(defaults to 0.00001 lumens or 100 stroops\). Transactions are final once they are in a block thanks to Stellar's Consensus algorithm, removing the need for handling re-orgs as would occur in a Proof of Work blockchain.
2. **Easy asset creation:** Stellar makes it extremely easy to create new assets and transfer them around. This makes representing state variables easier and also enables the creation of secondary markets where users can transfer these assets around in exchange for money.
3. **Horizon API:** Stellar's Horizon API makes it easy to query and post to instances that are full nodes. The API also gives a good interface to build transactions and do operations.
4. **Testnet that mimics mainnet:** The Stellar Development Foundation mimics mainnet on a testnet that it runs, making it easy to test features before deploying to mainnet. They also maintain a testnet faucet to get test lumens from.

## Alternatives to Stellar

While Stellar is good in terms of what it offers, it carries a few disadvantages as well:

1. **Limited opcode set:** Stellar's list of operations is extremely limited, possessing only those operations that are relevant in a payment/funds transfer setting.
2. **Questionable Security:** Stellar's mainnet and testnet have been down for multiple hours, and Stellar's quorum based consensus algorithm has a side effect of nodes trusting the Stellar Development Foundation's nodes since its enabled by default.
3. **Absence of verifiable on chain computation:** Stellar does not possess an on chain smart contract validation / transaction execution validation mechanism.
4. **Limited ecosystem resources and lack of exchange liquidity:** Though Stellar was started in 2014, it has failed to gain traction in terms of Stablecoin adoption, Merchant adoption, etc. THe liquidity in terms of stablecoin availability is also low.

Given these disadavantages, it is useful to explore alternatives that may address some of these concerns.

### Goals

The platform has a set of blockchain oriented goals which can be used to evaluate each alternative:

* **Trustless:** The platform must minimize trust in itself to avoid attack vectors centred around it.
* **Secure and Decentralised:** The platform must be backed by a secure blockchain without the possibility of attacks either by a coordinated hash power or by a small group of attackers.
* **Robust in functions:** The platform must be able to perform its intended set of functions in an easy, fast and secure manner without compromising on provided functions.
* **Good partner ecosystem:** Users must be able to get on the platform as easily as possible with minimal steps required.

More steps along with ratings are outlined here \([https://docs.google.com/spreadsheets/d/1H6HwnCwCMZ1yMZqEkVnr2Pw777mmAwhBQHiX1vnC9VM/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1H6HwnCwCMZ1yMZqEkVnr2Pw777mmAwhBQHiX1vnC9VM/edit?usp=sharing)\).

We note here that we omit contentious blockchains like Bitcoin Cash and Bitcoin SV whose development is highly volatile and centralised to a limited number of people in the ecosystem. We also omit blockchains like Tron, Ripple, and EOS whose development and funding goals aren't clearly defined.

## Bitcoin

Bitcoin uses an unspent transaction output \(utxo\) model. A transition to this model would require a fundamental change to the platform architecture. The platform should also maintain internal wallets that handle utxo selection, change outputs and similar which are common to an utxo model.

Bitcoin's list of opcodes is more expansive than Stellar and Bitcoin development in the future holds lots of potential for improvements and optimisations.

### Layer 2

Layer 2 \(L2\) is a term used to describe improvements that don't occur on the main blockchain. L2 can be imagined of as a layer parallel to the main blockchain which commits to the main blockchain at certain intervals or when certain criteria are fulfilled.

Popular L2 improvements on top of Bitcoin are the Lightning Network and Sidechains. Popular L2 improvements on top of Ethereum are Sharding and Plasma.

### Lightning Network

The Lightning Network \(LN\) is a peer-peer L2 payments layer. It offers fast and trust minimised payments that can be adapted to a variety of applications by changing the way the system is architected.

Each "peer" \(or "node"\) in Lightning is a user who either runs their own node or communicates with one. Each peer is required to have atleast one channel with another peer in order to pay others on the lightning network. The lightning network also has a Sphinx based routing protocol which can route payments from one peer to another.

Payments take place through peer to peer channels. Each peer has a balance associated with each of its channels, and the net balance of the channel is the sum of both peers' balances. Channels can be one or two way depending on the balance of each peer at each side of the channel. The ability of a given peer to pay another peer depends on the balances of all peers in between, or dependent on the liquidity of the route.

The lightning network requires liquidity from both participants in order to be effective. For a given peer, there are two types of liquidity - inbound liquidity and outbound liquidity.

Inbound liquidity is the capacity with which a given peer can be paid by other peers. The net inbound liquidity which is the sum of all individual inbound liquidities is the maximum amount a peer can be paid through lightning.

Outbound liquidity is the capacity with which a given peer can pay other peers. The net inbound liquidity which is the sum of all individual inbound liquidities is the maximum amount a given peer can pay other peers through lightning.

For a given peer, depending upon their role \(merchant, customer, payment processor, etc\), they can optimise their outbound liquidity. For inbound liquidity, they would have to form networks with other peers on the network in order to be reachable by other nodes.

Peers can create invoices in the form of QR codes or text messages. An invoice communicates to the payee the details of the requester, and once fulfilled, finds a route to the requester. Peers can also send text messages using the lightning network by paying all intermediary nodes to route the message for them.

A state in lightning is the balance on each peer's side in a given channel. This acts as proof \(in the event either peer acts malicious\) of the channel's balance, and doesn't allow any peer to claim other balances \(if they do so, the other peer can publish this proof to the blockchain and claim all the funds in the channnel\).

In opensolar's context, the platform can act as a central provider of outbound liquidity \(ie\) the platform has capacity to pay all entities on the platform. Investors must create inbound liquidity if they want to invest in projects while receivers and developers don't have to do so \(unless they want to donate to the platform or invest in a project\). Investors could also put in a default amount of money in a lightning channel once they sign up in order to be able to invest in projects immediately.

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

