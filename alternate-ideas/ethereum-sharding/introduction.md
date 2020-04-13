# Introduction

Sharding is a distributed systems idea where a single piece of data is split into multiple pieces and consistency is managed by an algorithm that communicates with the different pieces. Splitting data reduces data storage requirements, increases local read/write speed, and efficiency of individual shards. Each shard ultimately communicates with the other shards either during a fixed time interval \(eg: once in 30 seconds\) or through a protocol.

Ethereum has a big archival storage requirement due to a need to store state updates of all deployed and inactive contracts. Sharding Ethereum's storage provides faster transaction confirmation, and reduces storage requirements for running an Ethereum node. It also enables a shard to have its own set of rules, and these rules need not be reflected or communicated to the parent Ethereum blockchain.

For opensolar, one could use a two layer shard architecture where each platform lives on its own shard with its own set of rules, and communicate with a bigger openx shard which commits to the Ethereum blockchain. State updates can be fast, local and free, and proofs can be given to different entities once the platform once the parent openx shard commits to the Ethereum blockchain.

Like Bitcoin sidechains, this requires a shard explorer to navigate through the different shards. The shard explorer should contain details of a transaction or state update along with the block in which the openx shard committed the particular change to the parent Ethereum blockchain.

Shards need not necessarily be Ethereum based, they could even be different blockchains whose headers commit to the parent openx shard and/or the Ethereum blockchain.

The trust model for this involves trusting the openx shard and the platform shard, along with the parent Ethereum blockchain. If a shard owner tries to cheat an entity, the entity can submit proofs to ruin the platform's reputation.

