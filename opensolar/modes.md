# Modes

The platform has two modes - Testnet mode and Mainnet mode.

On testnet mode, the platform simulates a stablecoin called STABLEUSD on the Stellar Development Foundation's Test Network. This stablecoin acts as a replacement for USDx on testnet and is used to test and simulate stablecoin features. Testnet mode uses test lumens to facilitate payments and enable creation of assets. Test lumens are fetched from the Stellar Development Foundation's Testnet Faucet via the Horizon API.

On mainnet, the platform uses AnchorUSD as the stablecoin provider. Entities are required to purchase lumens and USD from AnchorUSD.  
  
In both modes, the Stellar Development Foundation's Horizon API and stellar-core instances are used.

