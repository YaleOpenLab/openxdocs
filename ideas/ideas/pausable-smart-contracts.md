# Pausable Smart Contracts

The Opensolar smart contract on AWS has multiple redundancy checks in place but in no event can a platform admin stop its execution once the project flow is in place. This presents problems for debugging because once a project's payback loop is stopped, it can only be started through the backend. As a result, arbitration is harder, and solving critical bugs in production becomes more difficult. A side consequence is that this presents problems from a legal perspective because the platform's execution can never be stopped, and this causes issues when getting legal approval for the platform. 

If the contract can be paused \(and not stopped\), it gives additional confidence to investors that the platform can step in if something goes awry and protect investors. This can also protect recipients and developers against malicious entities. A pausable contract also enables payment loops \(and the contract itself\) to be restarted while the contract is paused if a bug stops the contract's execution.

Pausable contracts also enable the addition of new conditions or the removal of conditions. These can be useful in the event some contract terms become outdated, and the entities involved want to change them.

