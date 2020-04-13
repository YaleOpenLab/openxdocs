# Disadvantages

1. **Less decentralised than Lightning:** Since the platform acts a a central coordinator for processing statechains, any of the previous owners of the utxo can collude with the platform to steal funds from a user. Such an attack will be public and does come at a reputational cost to the platform but the construction is more centralised than Lightning which does not have any such trust involved.
2. **Absence of assets:** Since Bitcoin doesn't support assets, there is no ready solution to adopt which can replace assets on Stellar. An alternative is to get rid of assets and handle only proofs.
3. **Slow confirmation times:** Bitcoin transactions are slower than Stellar transactions, so the platform can not afford to make a lot of synchronous payment requests during the investment workflow. This is a concern only when entering and exiting the statechain since transactions within the statechain are instantaneous.
4. **High Fees and whole utxos:** Bitcoin transaction fees vary widely, and sometimes it can be expensive to spend Bitcoin. This would affect entities entering and exiting the statechain. Statechains also require complete utxos and splitting utxos should occur as a transaction on Bitcoin-L1, increasing fees and wait times involved.
5. **Not time tested:** Statechains is a recent development, and hasn't been battle tested for security.

