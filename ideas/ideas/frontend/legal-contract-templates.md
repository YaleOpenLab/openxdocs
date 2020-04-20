# Legal contract templates

Projects on Opensolar require legal contracts to be signed between different entities like the receiver and developer, the investor and the platform, etc. These contracts are stored on IPFS, and their hashes are stored in the "Stage Data" field associated with each stage. Having templates for legal contracts on the frontend \(eg. a docusign iframe\) makes this process easier, and the platform can store relevant data without much user intervention.

This enables faster processing of documents, and legal entities can register on the platform and provide these services directly. Having a central repo of contract templates also enables other platforms to borrow and adapt these to their application, saving them time and money associated with the legal process.

This would require the use of an existing digital signing application like DocuSign to be embedded within the platform, and the addition of functionality that enables users to sign documents, add new documents, etc. Once signed, documents must be stored on IPFS and the hashes stored as part of a project's details in order for them to be retrievable by other entities.

