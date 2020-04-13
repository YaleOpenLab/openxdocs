# Disadvantages

1. **Need to manage liquidity:** Since the platform acts as a central provider of liquidity, it maintains a non trivial balance of Bitcoin in open channels and it should manage these balances efficiently. Failure to manage balances efficiently could lead to the platform's inability to open new channels and therefore increase costs. Maintaining channel balances also means there's an amount that is constantly locked and not spendable.
2. **Need to handle channel closing:** Since lightning is a channel based infrastructure, the platform should be adequately equipped to handle channel closures \(both by the platform, and by the entities on the platform\). An alternative might be that the platform does not offer channel closures to entities on the platform though this comes at the cost of reduced decentralisation.
3. **Handling large payments:** Lightning is still in its infancy with respect to channel capacity and large amounts that need to be transferred sometimes fail to find a route. One way to handle this is by ramping up channel capacity on the platform's end as needed although this would conflict with 1 above, and make liquidity handling more difficult.

