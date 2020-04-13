# Introduction

Statechains is an improvement on top of Sidechains, combining the Hub and Spoke model of LN with the semi trusted nature of Sidechains. Statechains requires a centralized coordinator which communicates with the others in the system, and an internal index that maps utxos to owners.

An entity that wants to enter a statechain can do so by creating a 2/2 Multisig address with the central coordinator "C". If "A" would like to transfer to "B" an utxo "X", it passes the private key "x" to B through C. C checks if A is indeed the owner of X, adds its signature and broadcasts it to the blockchain, and updates its internal map to reflect that B is the new owner of the utxo. A is required to delete the private key from its storage. Even if A maliciously stores the private key and attempts to spend it elsewhere, C refuses to sign the mutlisig transaction because its internal map shows that A transferred ownership of X to B at a point in the past. It could also penalise A for attempting to spend such an utxo by removing it from the statechain.

In Opensolar, the above can be mitigated by not exposing individual utxos to users. The platform can act as the centralised coordinator and investors can transfer utxos to the platform conditional on the investment threshold being reached. In the event the threshold is not reached, the utxo's ownership and the platform's itnernal mapping will not change.

Once the investment threshold is reached, utxos are transferred to an intermediary, and spending from the intermediary requires coordination between the receiver and platform. When the receiver wants to pay certain entities, it requests the platform to sign the transaction, and the platform subsequently transfers ownership of the utxo to the other entity.

Statechains can support multiple currencies that follow an utxo model, and users can choose to swap currencies within the statechain. This gives flexibility to the receiver, who can pay entities in other currencies.

Statechains requires Schnorr signatures as a minimum upgrade to the Bitcoin protocol. Statechains can also be used in combination with payment channels, and people can use these utxos to fund a channel between two peers.

The trust model for this idea relies on the platform not acting maliciously or in collusion with one of the previous owners of an utxo. In the event this occurs, proofs of ownership are easy to publish, and the platform's reputation will be at stake.

