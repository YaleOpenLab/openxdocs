# Local IPFS map storage

Currently, IPFS state updates are handled as transactions made towards one's own Stellar account, and people need to use a Stellar explorer to find the memo \(which contains the IPFS hash\) associated with the 2 state update transactions. Instead, the platform could maintain its own storage where it shows hash details and data, and a user can choose to verify the shown data using a third party IPFS explorer.

