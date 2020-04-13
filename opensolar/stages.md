# Stages

Opensolar uses a project based investment model - recipients advertise projects which investors can invest in. Projects are divided into multiple stages:

Stage 1: **Engagement**  
Stage 2: **Quotes**  
Stage 3: **Signing**  
Stage 4: **Investment**  
Stage 5: **Construction**  
Stage 6: **Interconnection**  
Stage 7: **Legacy**  
Stage 8: **Handoff**  
Stage 9: **End of Life**

Each project is required to go through this lifecycle. An entity performs its role in a set of stages \(eg the investor performs its role in stage 4, originators in stage 1\) and data associated with a stage \("Stage Data"\) references entities' actions in that stage. Stage progression is trigerred by a combination of manual and automatic events. Stage data is stored on IPFS \(Inter Planetary File System\) and the reference hashes are stored on the platform's internal database. Stage data is reviwed by admins and other entities before a stage upgrade is approved. For some stages like stage 4, data is reviewed from the blockchain and the stage is automatically upgraded.

Some data is determined by oracles who attest to statements \(an example is neighbours attesting that the energy rate charged for the month is the same as the receiver claims it is\).  This data is combined with other data associated with stage and committed to IPFS.

Some projects can skip some stages if they are not relevant to the project. For example, a donation project where both the contractor and developer is same as the entity donating the energy grid might not have stages 1, 2 and 3.

