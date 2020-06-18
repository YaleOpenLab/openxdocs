# Blockchain

## Alternate blockchains

Opensolar is currently built on Stellar but there are proposals for building Opensolar on an alternate blockchain ecosystem. This can be done in parallel to Opensolar in order to compare both platforms and arrive at a list of advantages and disadvantages. More details and ideas for these are outlined in the "Alternate Ideas" section.

## Hardware Wallet Support

Currently, Stellar seeds are encrypted with the seed password and stored on a database on the paltform's backend. Having hardware wallet integration would mean that users who manage their own keys \(ie users who are more security conscious\) can invest in projects on opensolar if they have a hardware wallet like Trezor or Ledger.

If a user chooses to connect their hw wallet, we should not import their seed onto the platform - rather the flow must be in such a way that the ycan invest one time and there's no seed interaction with the platform after that. This would blend in nicely with the emulator CLI and could borrow certain upgrades from there.

## Investments using other assets

Currently, the platform can only do stablecoin investments in projects. Having XLM investments in projects is easy if the project's threshold is in XLM. Investing using other assets on Stellar is also useful in expanding the reach of the platform.

Assets can be exchanged for stablecoin / the native asset of the project on the Stellar DEX in real time to simplify internal handling. When withdrawing, the investor can specify the asset they want and the platform can once again exchange the native asset for the desired asset. Having an internal matching engine makes this process easier.

## Manual smart contracts

Contrary to pausable smart contracts, a manually trigerred smart contract is when a platform admin can immediately move a project to stage 4 for investment, or to stage 5 after post-investment to start the teller workflow, etc. This is useful in cases when automatic flow breaks or is not necessary since the platform admins have already approved the stage transition earlier.

It also helps in cases when the receiver defaults on payments, and the investors together decide to change the terms of investment. For stage transitions like stage 7-8, admins can review stage data and transition stages manually since there is no end project state defined for a project.

Manual smart contracts are extremely useful in combination with pausable smart contracts since they provide power to platform admins to regulate the functioning of the platform. These functions could also be used by an enforcement agency like the SEC.

## P2P Matching Engine

The platform should have an internal matching engine which can match investors who are investing and recipients/ developers who wish to withdraw funds from the platform. This avoids the need for either side to wait for AnchorUSD to process deposits and withdrawals. An internal matching engine would work closely with an in house DEX to process orders.

A matching engine also provides for interesting possibilities on investments \(a person willing to sell their investment can be matched with a person willing to buy directly\) and recipients \(a recipient wishing for investment in a project can ask previous investors or investors in other projects and match directly\).

## Parallel blockchains

Along with Stellar, it would be nice to have a layer that exists in parallel to Stellar providing on-chain smart contracts and verification. Assets and financial payments can continue to take place on Stellar. More details and ideas for these are outlined in the "Alternate Ideas" section.

## Pausable Smart Contracts

The Opensolar smart contract on AWS has multiple redundancy checks in place but in no event can a platform admin stop its execution once the project flow is in place. This presents problems for debugging because once a project's payback loop is stopped, it can only be started through the backend. As a result, arbitration is harder, and solving critical bugs in production becomes more difficult. A side consequence is that this presents problems from a legal perspective because the platform's execution can never be stopped, and this causes issues when getting legal approval for the platform. 

If the contract can be paused \(and not stopped\), it gives additional confidence to investors that the platform can step in if something goes awry and protect investors. This can also protect recipients and developers against malicious entities. A pausable contract also enables payment loops \(and the contract itself\) to be restarted while the contract is paused if a bug stops the contract's execution.

Pausable contracts also enable the addition of new conditions or the removal of conditions. These can be useful in the event some contract terms become outdated, and the entities involved want to change them.

## Run own stellar core and horizon instances

Opensolar currently uses services run by the Stellar Development Foundation for interacting with the blockchain. The platform running its own core and horizon instances reduces dependency on the SDF, and might help handle transaction relay problems with SDF's horizon API. This however, doesn't solve problems with the consensus protocol that make Stellar centralised, which is explained in detail in the "Alternate Ideas" section.

## Scheduled Investments

Companies with a good CSR policy are looking to constantly invest a fixed amount of money in projects. Having scheduled investments where such companies can invest year after year is good for the platform to gain mroe traction in the commercial space.

Companies would be required to specify a list of characteristics based on which the scheduled investments will be selected. These can be energy type \(solar, wind, etc\), location, risk factor, desired returns, and much more. Once these constraints are specified, the platform continuously looks for these projects and invests in them if the required time frame for investment has arrived. Having ETFs or bathched investments makes this process easier since CSRs can select their projects directly.

## Stellar sidechains

There are ideas for Sidechain implementations in Stellar based on ZkVM and other architectures. Having sidechains 

1. Helps offload transactions and state updates to the sidechain
2. Helps improve performance
3. Reduces fee impact of the platform

This is similar to Bitcoin sidechains described in the "Alternate Ideas" section.

