# Rescuer

Rescuer is a feature of openx that enables an admin to perform emergency functions using the platform's seed. The rescuer can:

1. Transfer funds to another address
2. Sweep all XLM funds from the platform
3. View platform balances
4. Sweep XLM from a project's escrow
5. Send USD to another address

These functions are extremely useful in the event the platform is hacked or there's a bug in the contract that cuases people to lose funds.

The rescuer is a CLI based tool and does not have a web interface. It must be run by admins and requires the platform's seed to start.

