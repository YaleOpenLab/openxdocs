# Frontend

## Changing User-Entity Architecture

Currently in Opensolar, the user entity is the base class that other entities on the platform build on top. This however, has a disadvantage since it means different entities have the same publickey. To avoid this, a potential construction is to make create new users for each entity and somehow have something on the importing platform's end to identify that they all are indeed the same user.

This could also be done on openx's side by introducing a new base class called the "entity" which allows for supporting an array of public keys and encrypted seed passwords. The base user class' publickey variable could also be converted into an array and new publickeys can be added whenever the user desires so.

## Collective Investment

A group of investments similar to an ETF or a set of mutual funds in the traditional finance world is useful to balance risk and investment return. For opensolar, that would mean balancing between different energy types, locations and returns. The platform can curate a collection of projects based on defined parameters and offer them to investors who would like to invest directly without diving deep into individual projects. This is also simple for companies which would like to manage a comprehensive portfolio of clean energy projects while balancing risk and returns.

This also blends in well with CSR initiatives since CSR heads can simply navigage to openx and invest in a specific collection.

## Corporate CSR mode

CSR arms of companies must be able to invest in groups of projects as quickly and efficiently as possible. The backend can have a simplified workflow for these companies \(they would have to fulfil KYC / AML regulations however\) where investing is easily enabled and access control is tuned towards the internal structure of the CSR arm.

## Create your own contract

Right now, the platform uses a predefined smart contract with the project threshold as the only changeable parameter. Having a web based interface for originators and receivers to tweak other parameters and create their own smart contract enables them to come up with new ideas that existing contract creators may not encounter, and ideas that are exclusive to the project they are requesting funding for.

This greatly aids the expansion from solar energy projects to other types of investments since people can define their own conditions. It also gives entities flexibility while designing various parts of the contract like payback period, investment models and more. Some part of the contract however would be fixed and editable only on the backend or by project admins.

An advanced feature would occur when receivers would like to incorporate higher level of detail within their contracts. Such receivers would have to make a Pull Request to the platform's repository and upon approval and deployment, can incorporate the new contract for their project. The review process should ensure there are no bugs that would cause users to lose funds, enable certain enttieis to defraud other users, etc.

## Database Mode

SEC and other regulatory agencies are wary of the terms "blockchain" and "cryptocurrencies". Having a blockchain free mode which is powered by a raw database can help platform founders navigate this territory. This mode would be totally similar to something like Kickstarter, except that it open source and still connected to the overall openx architecture.

## description: Developer oriented subdomain

## developers.openx.solar

We could have a separate developers.openx.solar similar to Facebook Developers or Twitter Developers where developers can request new tokens, register new apps, etc. The developer page could also have instructions on the steps necessary to setup openx/solar on local, docker images and more

## Dynamic Stage definitions

Currently, Opensolar hosts stages that are fixed and cannot be changed by receivers or other entities if they wish to do so. Having dynamic stages \(eg, a project can choose to have only 3 stages\) gives more flexibility to the receiver to define stages associated with their project.

This would also involve changes to the `StageData` field, which would become dynamic in order to support the stages defined by the receiver.

## Emulator upgrades

The emulator emulates certain functionality of the backend but does not act as a complete replacement to the web interface. The emulator is useful to test functionality of the backend that is not yet present on the frontend. This should be expanded to include the full functions of the backend so users who don't want to trust a web interface or users who don't want to wait for features to be implement on the frontend can still interact and perform functions within the platform.

The emulator could also be combined with the teller to offer a singular interface for people to interact with opensolar through the CLI. This would enable recipients to access a broader set of features than the Teller, and enable investors to monitor the teller directly though their CLI.

The emulator could also be packaged as an Electron app and run as a standalone web interface. Alternately, the web interface could be packaged as an Electron App and offered to users who wish to run their own web interface.

## End project state

Currently, projects on Opensolar do not have an end state but it is necessary to retire projects once they reach stage 8/9 and display relevant data to investors and recipients on their dashboards. This would help keep track of how many projects have been completed and these projects could be displayed in a separate screen similar to the Explore Screen.

An extension of this would be handling the hand-off event where the ownership of the solar system changes from investors to the recipient. This handoff event could include the signing of a legal contract template which requires signatures. The document once signed will be stored on IPFS and the recipient can use it as proof of ownership in a legal context. Alternatively, end project states could be triggered by platform admins and notifications can be sent to all project entities.

UPDATE \(6/1/19\): An end project state had been created, admins can now set a project to complete or not complete through the admin dashboard interface. The integration around transfer of assets to the recipient still remains, and the admin dashboard does not have a web interface design yet.

## Fiat support

Supporting Fiat Currencies \(USD, EUR, etc\) on the platform can greatly help increae the number of people who would like to be part of the platform. Fiat support through Stripe or PayPal should be relatively easy through their APIs although they may require documentation to support the platform's use case and viability.

A project can choose to accept fiat funding or the platform could enable it by default. When investing in the project, the platform could ask for the investor's preference on the confirmation page or on the starting page \(where balances are displayed\). If there are excanges interate wth opensolar, the platform could use the exchange's APIs to switch between muiltiple currencies and have only one base currency.

## Georestrictions

There are certain regions which are banned from communicating with other regions due to international sanctions or due to domestic restrictions. Since the platform is based in the United States, it must comply with these laws and the platform must be unavailable to investors from these regions.

A dynamic geo-restriction policy would detect the source ip of the requester, and ban them from accessing the page. One could also detect if the user is using a VPN or Tor and refuse to server users if regulations deem so.

A static geo-restriction policy would add ip blocks to iptables in order to refuse traffic from the banned clusters. This would be hard since there are tons of ip blocks belonging to these banned regions, and we would need to add a rule for each one of them.

Georestriction can also be done through the use of DNS middleware like Cloduflare which can automatically filter traffic based on source. Using these APIs however cedes DNS control to the middleware, reducing overall security.

## Goal based funding

Platforms like Kickstarter have goal based funding schemes ie a receiver can define a set of funding goals and each goal has a set of benefits. For opensolar, the first goal could be installing a 1MW panel, the second could be installing a 5MW panel, etc. Each goal has benefits associated with it, and investors would receive returns based on the goal stage they invested in.

This would require a modification to the way stages are presented right now to invlude support for goals, and would also require the addition of several UI components to display the goals and the number of investors at each goal stage.

## Immediate Payment Confirmation

When using Walmart, the checkout process is very fast - you enter your CC/DC details and right away, you're taken to the payment confirmation screen. The actual payment doesn't happen until about 2 hours later, failing which the order stands as not confirmed and an email is sent to the buyer.

A similar workflow could be done in opensolar where investments are confirmed immediately \(while the blockchain processes occur in the background\) and users are sent emails if their investments didn't go through. This avoids the need to wait on a particular screen for confirmation \(which currently takes about 30s\).

## In Platform Notifications

Currently, notifications are sent via emai lto entities involved in a project. An improvement to this would be if we can have notifications inside the platform \(probably a different section\) where the entity can view a list of the notifications that they have received.

Having in-platform notifications also makes it easier to send messages and create custom prompts \(like "Enter your seed password to accept your investment"\) which would otherwise be tough while sending notifications through email.

## Integration tests

The platform has unit tests for different modules but there are no integration tests which can test functionality that requires intervention and user interaction. Integration tests help test the end-end flow of the platform, and changes to code that affect this flow can be easily identified. Integration tests also help catch edge cases and help prevent breaking changes from being merged into the codebase.

Integration tests need not be restricted to Golang, they can be in Python or other languages too. Tests need to be run on Travis CI so new Pull Requests to the repo can be thoroughly tested before being merged into the codebase.

## Investment Tiers

Having investment tiers like Gold, Silver, Bronze, Institutional, etc helps investors easily navigate to their desired projects based on the scale and amount of risk that they desire to be associated with their investment. Investment tiers could also be displayed as badges on an investor's profile so receivers know what kind of investments they are getting towards their projects and can engage with them more effectively.

## Investor rescue fund

BitMEX has a "rescue fund" which it uses to refund investor on the platform in case there's a hack or htings go wrong on the platform. Openx/solar could have something similar as well to protect investors, recipients and all other entities involved. Funds to this account would be accumulated through extra fees whose proceeds go directly to the investor rescue fund.

## Kubernetes Platform Cluster

Kubernetes enables easy maintenance of individual components through the creation of clusters, manages uptime in an efficient manner through the creation of pods and manages scaling by creating new pod instances when required. The Kubernetes cluster for the platform would be composed of:

1. An Openx instance
2. An Opensolar instance
3. A teller instance
4. A web interface
5. A builds instance

Each cluster can be created and deployed through config files, and these config files can be made open source so others can easily replicate this functionality.

Update \(6/1/20\): Kubernetes configs have been added to both openx and opensolar. Deployment along with required pieces is still pending, which should ideally be left to devops.

## Local IPFS map storage

Currently, IPFS state updates are handled as transactions made towards one's own Stellar account, and people need to use a Stellar explorer to find the memo \(which contains the IPFS hash\) associated with the 2 state update transactions. Instead, the platform could maintain its own storage where it shows hash details and data, and a user can choose to verify the shown data using a third party IPFS explorer.

## Messaging Service

Most platforms and websites today have something similar to Intercom which makes getting help and support easy. On the platform ,we could have something similar to Intercom where entities can ask their questions directly to platform admins or support staff.

An improvement on top would be a live chat option where entities that are in the same project can talk to one another via the platform \(instead of sending emails through the platform\). This would be similar to AirBnB's in platform messaging service which enables parties to talk to one another. These messages can also be used in event of arbitration where the platform admin can cimply create a channel with all entities involved and communicate with them at once to resolve the issue.

The messaging service could also provide features which enable messages in the project channel to be broadcast to stage data. This reduces interaction from the user, and enables easy verification of what's being stored in the stage data field.

## Multiple Tellers

Having multiple tellers is a powerful primitive to be able to accurately keep track of the energy generated, and the amount to be paid back to investors. There could be different tiers of Tellers:

1. Monitoring Teller run by the platform
2. Reporting Teller run on the IoT device
3. Watchdog Teller run on a third server, connected to the IoT device and the monitor

This could prevent malpractice on the receivers' end and on the platform's end since the data stream is no longer singular. This could also reduce the lead time of deploying fixes to the Teller since two pieces in the above flow \(monitoring and watchdog\) can be updated as soon as stable updates are available.

## No Javascript mode

Javascript has a set of vulnerabilities that some users are wary of, and as a result use a no-js environment to avoid scripts being run in the browser. Having somethign similar in openx/solar would involve the creation of a pre-compilation step which compiles the javascript on the web interface and serves it directly to the user.

## OAuth for Openx

OAuth is a standard protocol used for login by Facebook, Google, Twitter, etc that makes cross site login and integration easier. For openx, that would mean cross openx-platform registration is as simple as generating an OAuth token and adding a button that says "Login with openx". This button is similar to "Login with Facebook" and can be placed on any website as long as there's a token associated with the button.

## One Click Invest

Platforms like Amazon have a "One click" checkout feature which navigates users directly to the final confirmation page without displaying the steps in between. This makes use of a combination of default payment methods, shipping addresses, etc in order to not prompt the user to fill in these details.

One click invest is useful for returning investors who've already vetted the project, and are back just to invest in the project. It is also useful for people who want to invest small amounts in projects and don't want to worry about vetting projects. This can help in donation projects where people can just display the one click invest link and ask for donations.

## Other language ports

Opensolar and Openx are written in Go but it would be nice to have Javascript or Python ports so people can easily incorporate openx into their applications. Having an npm package or a pip repo is extremely useful to import functionality and test auxiliary features that are better available in these languages.

Having other language ports also makes a potential transition away from Go easier. For eg, if the RPC API is to be shifted from Go to Javascript, having a JS package makes the transition easier than having to do it from scratch

## Pilots with other ideas

Currently, Opensolar is targeted at solar energy projects but an alternate implementation with fractional housing, or peer to peer loans helps expand the horizons of openx, and helps tests the utility openx provides for next generation investments. Opensolar used to house a fractional owenrship Proof of Concept in the repo before but that has now been abandoned due to a lack of progress. Potential applications that could be run as pilots include:

### Decentralised community infrastructure

1. Water
2. Housing
3. Transport
4. Power
5. Waste

### Climate finance

1. Forest-based project
2. Regenerative agriculture
3. Energy efficiency programs
4. Adaptation infrastructure
5. Biogas

## Platform Blog

The platform could have a daily / weekly / monthly blog where admins post on a wide range of topics. The blog could feature experiences by entities, projects that reached completion, projects that are new to the platform, etc. It could also have sections within it \(technical section, news section, etc\) and each section can have its own cycle of updates.

Having a blog helps increase the reach of the platform beyond entities interested in participating. It also keeps activity around the platform active, and builds a community around openx.

## Platform Help Bot

Some platforms have a bot or a guided user interface which helps guide them through various parts of the platform. This bot also helps clarify a list of basic questions \(similar to the bots on Intercom\) and helps receive preferences, etc. Opensolar could make use of a bot performing the following features:

1. Guiding users through the platform
2. Open questions and templated responses
3. Ability to guide users to different pages when askes questions
4. Ability to change user preferences, etc when asked

## Private investments

Some investors might not want to reveal their investment amounts, or sometimes even their public keys. To obscure investment amounts, one idea is to transact multiple times between the investor and platform, and the net sum of all these transactions would be the investor's investment in the project. To obscure their public key, they could transfer funds to the project indirectly or transfer to a one time address possessed by the platform and link paybacks to a new address they control. This would obscure the trail between an investor and the platform.

Other ideas are using ZCash and other privacy focused coins for project investment. This would involve enabling investments in two currencies in one contract.

## Promotional Offers

In order to get more people interested in investing, the platform can provide a set of incentives like promotional offers and referral codes which provide bonuses or discounts on investment in projects on the platform. The goal of these should be to get more entities participating in projects on the platform and not at just getting more signups or user registrations.

These promos could be targeted at a single platform like opensolar or towards all projects on openx. Ideally, admins must be able to generate these codes from the admin dashboard, and monitor response from the same interface.

## Quadratic Funding

Quadratic Funding is a new donation model popularised by Glen Weyl and Gitcoin. It proposes a quadratic matching scheme as opposed to a linear scheme to avoid gaming of the system and gives more emphasis to smaller donations.

Quadratic Funding would be a nice model to have for donation projects and for investors looking to match donations towards specific projects. Integration with Gitcoin can also be part of this, presenting further interesting applications.

## Real Time Oracles

Currently, we make use of a static oracle that fetches the price of elctricity in Puerto Rico from the backend. We could have a dynamic oracle which fetches the electricity price in real time and feeds it to the frontend. This would work closely with the ability for neighbours to report electricity price in the area which would then be averaged to find the electricity price for the installed project.

## Replace MQTT with TLS

MQTT is a lightweight protocol that is useful for IoT devices to communicate with each other but TLS is a more robust solution that can be used for a variety of applications. We should simultaneously have MQTT support for IoT devices and TLS support for more complex devices.

## Secondary markets

The platform can make use of the Stellar DEX to offer a secondary market to investors who can exchange one type of project assets for the other. Secondary markets can enable the exchange of one project's INVAsset for another, and one project's DebtAsset for another. This greatly helps an investor balance their portfolio with a collection of safe projects and risky projects.

Recipients could also potentially transfer DebtAssets to other asset holders or even a bank in exchange for short term collateral. This would help bring in investors who couldn't invest when the project was in a stage for investment but want to do so later. Investors wanting to exit Opensolar can easily do so by selling their INVAssets to other investors.

In essence, a secondary market can be compared to a platform's internal Stellar DEX using the Stellar blockchain for settlements. Running an internal DEX helps mitigate traditional fees associated with using the Stellar DEX.

## Social Media Signup

Social logins using Google, Facebook and Twitter are easy to add using standard buttons. The platform would need to pull in the name, username and email address by default and take the user to the profile settings page where they need to setup a password. We should also send a confirmation email to the user to verify their email address.

## Split JSON-RPC API

The JSON-RPC API is in the rpc package of openx/opensolar. To make things easier and in order to add more functions to the API, we should consider splitting it from the main repositories into a pure Javascript based API.

Using Javascript for APIs is standard and comes with many advantages like REST conformance, easy parameter handling, and easy request parsing. Using JS also makes it easier for more developers to work on the API-Frontend integration since both parts will be in JS. JS also has more open source presence, and might help increase contribution traction for the project.

Splitting the API also improves overall modularity of the platform since cross-language part communication would occur within the platform. Security might be improved if this API server is hosted separate from the main openx server.

## SQL database

Opensolar currently uses boltDB - a key value pair database with limited functionality and room for scalability. Migrating to a SQL database would help create relations between different entities on the platform \(eg between investors, users and recipients\), help create a good database structure, and be more scalable.

PostgreSQL or MySQL are ideal options to look at since they are designed to be used in production environments. Migrations requires the contruction of a detailed database architecture, with entities being linked to each other, the user entity being imported as a foreign key, etc. Migration would also require migration scripts which can successfully migrate data from boltDB without loss of information. Having a database architecture also enables easy audits of storage infrastructure, and one can easily understand how different parts of the backend interact with each other.

## Twitter Tipping Bot

Similar to Bitcoin and Bitcoin Cash tipping bots, there could be an opensolar tipping bot which can enable investments in projects with minimal effort. This would be an interesting side project and in the future can be extended into an external plugin for websites which can request for donations through opensolar.

The both could also offer additional features like viewing the status of a project, listing all projects, etc through twitter's Direct Message \(DMs\) which would help bring non tech uses onboard the platform.

The tipping bot could theoretically accept investments in any currency with a minmum investment amount and exchange the received amount for a project's native currency through an exchange's APIs

## Using KMS

Currently, the platform seed is encrpyted but the platform seed password is sdtored in the config file used to start openx/opensolar. The platform seed could instead be transferred to a Key Management Service and we can call the platform seed by calling the KMS API.

Using a KMS encrypts storage by default, so we don't have to worry about secrets being leaked. A KMS also provides high security guarantees and uptime, so the platform seed will not be lost if the server doesnt' work.

A KMS is easy to implement if we move to a docker based architecture since the secrets can be served directly to the container / server instance through AWS IAM roles.

We could also use hardware keys to act as a KMS, and configure the server to use the keys from the hardware device. This improves security since the keys don't reside in a "hot" interface. This however, is better implemented in a self hosted service \(ie a service where openx/solar runs its own hardware\) since configuring hardware keys with AWS or other hosting providers can prove to be tough.

## Verified accounts

Verified accounts \(similar to "blue check accounts" on twitter\) are accounts whose credentials are verified and they are presented with a badge that shows that their account has been verified. This helps prevent bots, spam users, etc whoi might impersonate others and try to steal money from entities on the platform.

Verified accounts can also be used in the context of companies whose KYC information has been verified \(eg. Coca Cola could have a tick if their company's representative uploaded the necessary docs to prove that they really are from Coca Cola\).

## Virtual dev sandbox

Currently, we have a sandbox on the backend that can be customised and run be people who want to test and run Openx/solar. Having a virtual sandbox \(similar to some courses where there's a terminal on the right and there's text on the left\) would be immsenself useful for people to easily visualise how openx and opensolar interact, and also enable people to readily test out features that they wish to implement.

This would ideally require that a client side terminal be run on the website somehow. Katakoda \([https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-interactive/](https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-interactive/)\) is a good example and can be imported for what we seek to accomplish.

## Web SSH for admins

Right now, admins can access the openx server only by having access to aws root credentials. In the future, admins might want to view debug logs, change modes, or perform emergency backup and it is easier to provide a web SSH UI with limited functionality to achieve this.

A web SSH UI would also enable real time logs on the admin dashboard which is extremely useful to monitor investments, thwart attackers, etc. It also helps non devops admins handle and report emergencies easier.

## Wire protocol

Currently, platforms communicate with each other through SSL/TLS. The creation of a wire protocol that can accomplish this would be very useful since it would improve speed of communication and enable the creation of CLI clients using which platforms can interact with each other.

An example of this can be viewed in the Lightning Network Protocol where peers talk with each other using the Noise protocol.

## Yubikey / U2F support

U2F is a secure 2FA Authentication protocol used by hardware devices to generate 2FA codes. Yubikey and U2F support could be added in for 2FA login so people can use secure hardware based 2FA tokens.

