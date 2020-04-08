# Smart Contract

The Opensolar smart contract runs on AWS since Stellar does not support on chain smart contracts. It contains core functionality surrounding investments and payback whereas auxiliary features that handle transactions like asset creation are imported from sub-packages. The smart contract also allows for different investment models which can be defined in a relevant sub package. By default, it uses the munibond model for investments.

