# Ethereum


Ethereum uses an account based model similar to Stellar. Ethereum provides a Turing complete on chain smart contract abstraction \(called the Ethereum Virtual Machine or EVM\) and global state variables. This eliminates the need for assets on Ethereum. As a consequence, the opensolar smart contract which runs on AWS could migrate to the Ethereum blockchain.

Ethereum provides a wide range of opcodes to work with, and arbitrary functionality can be implemented. Ethereum charges "gas" for each computation performed on chain. For common operations like hashing, adding, multiplying and state updates, Ethereum fixes the amount of gas that is charged. For other operations, a variable amount of gas is charged. Transaction fee is denominated in ETH. Gas and ETH are subject to their own fee markets.

The EVM is a powerful abstraction for developers developing on chain smart contracts. Running smart contracts on chain provides provable execution without having to provide commitment proofs for computation. An on chain smart contract also improves auditability of a contract since one can easily check if the code on the repository is the same as the code deployed on the blockchain. This enables third party monitors to monitor updates / investments on the platform. Third party services can also create their own web interface, and for the contract to create their own instance of Opensolar.

Ethereum has a large developer ecosystem and lots of potential ideas and applications that can be used without much effort. These applications can augment the platform and enable the intersection multiple ideas.

Ethereum has L2 solutions similar to Bitcoin \(eg. Plasma\). Ethereum is transitioning to a Proof of Stake system where miners stake ETH to take part in consensus instead of hashing. Ethereum also has provisions to incentivize developers to work on projects through decentralized crowdfunding ideas \(example Gitcoin\). This could be a mechanism to fund development and bounty programs on opensolar.

Ethereum's EVM offers a powerful on chain smart contracting interface. This can be used to offer verifiable contract execution on chain, global state variables, etc.

The platform's contract can be deployed on chain and entities would interact with the contract through standard tools available on Ethereum. Investment proofs, state variables are all stored on chain so there is minimal requirement for an in house database that serves these functions.

Ethereum-L1 can also be used in parallel with blockchain system. For example, payments can take place on Bitcoin, and state updates and storage can take place via Ethereum. This gives the dual benefit of low fees while still having auditable smart contracts on chain. This case is a slight variation of the bridge scenario described earlier.