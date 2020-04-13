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