# Frontend

## 2FA Login

The backend has provisions for Google-2FA based login but the frontend does not have the required screen and API integration yet. Investments should not be allowed until investors have setup their 2FA credentials to prevent claims of loss of funds, fraudulent investments, etc.

2FA can also be used in place of the seed password if the user desires so and the screens for seed password confirmation need to be altered to provide for this.

## Asset Transfer UI

Currently, the P2P asset transfer User Interface is not intuitive and does not realise all the features that P2P assets on Stellar offer users . Having a good in terface could enable the easy creation of a secondary market where users can trade their assets with one another, create new assets and issue to users. Another application is hwere people could transfer AnchorUSD among themselves without requiring to go through the KYC process themselves.

## Auction Dashboard

Currently, the following types of auctions are supported on the backend:

1. Blind
2. Vickrey
3. English
4. Dutch

A recipient can choose from any one of the above criteria towards choosing a final project from a stage 2 \(contractor proposed\) project. The frontend must have a screen that calls the relevant backend handlers and accompleishes this.

## Comments section / Forum

Having a comments section on a project's page similar to Kickstarter's comments section is useful for investors to ask questions directly to the receiver. All comments are public, so peopel who have questions can go through the comments section to see if their query has been addressed.

An alternate approach is to have a forum for all things related to openx/solar covering all aspects of the platforms. The forum would require a common login with opensolar to import details like name, projects, etc.

Both approaches would need moderators to police content being posted and remove comments that are inappropriate or irrelevant. This could be done by community members appointed as mods or by admins of opensolar.

## Common Dictionary

For many people, climate change terms are daunting at first and they might find it difficult  to understand what the project really seeks to accomplish, what is being built, etc. For this purpose, having a t erms dictionary which can list all the common terms related to Solar Energy is immensely useful to lower the knowledge barrier needed to invest in projects on Opensolar.

This could be designed as a simpel map stored on the backend which is editable only by admins.

## Compiled investment statistics

The frontend can call a range of different APIs to display cumulative investment statistics that can be shown to investors. Ideally, the statistics must be displayed in a graphical format by using a library like d3.js 

## Content Management System

**Implementing a Content Management System \(CMS\) on the frontend:** Opensolar requires a content management system in order to manage frontend content. Content is further divided into the following sub categories:

* **Project content:** Project details and content needs to be editable by originators and receivers. Currently, this is done by changing parameters on the backend but this needs to be moved to the frontend where people can change content as desired. This would also be supplemented by a design for the editable interface which would allow users to easily change data and move things on the frontend.
* **Developer engine:** The developer engine is one of the core pieces of the Opensolar platform. The engine enables developers to specify project details, give project quotes and continuously manage infrastructure. The developer engine should closely work with the backend to communicate project requirements, and should have a clean interface that enables developers to communicate their needs and suggestions.
* **Investor dashboard:** Currently, the fields displayed on the investor dashboard are fed from a rudimentary backend CMS. This handling should be shifted to the frontend and the frontend should define the structure and content of the page. This should be communicated to the backend through an API endpoint. Each field on the dashboard must be modular, and an investor must have the option to add additional fields to their dashboards.
* **Receiver dashboard:** Like the investor dashboard, the fields displayed on the receiver dashboard are fed from a rudimentary backend CMS. The receiver dashboard has the same requirements as the investor dashboard and an additional requirement in that the teller dashboard should be linked or be a part of the receiver dashboard. The teller dashboard should have details on the teller like device id, data generation history, mqtt broker credentials, etc. The teller dashboard could also have functionality that enables a recipient to remotely SSH onto the IoT device deployed so they can view what's happening directly. The teller dashboard also ensures good accountability regarding the data generated on the device, and enables project entities to keep track of project progress.
* **Admin dashboard:** Opensolar has a list of admin API endpoints using which admins can perform a variety of functions on the platform like viewing all pending projects, flagging users and projects, and approving KYC credentials of a user. These functions do not have pages on the frontend yet, and designing and developing such a page would be useful for platform admins. There could exist a separate login page for admins at openx.solar/admin and admins can login and access the admin dashboard without having to navigate through the platform.

## Dark Mode

A dark mode slider which switches the color of the web interface is a useful vanity feature. This slider can be placed either on the settings page or as a popup on indivdual pages.

## Data visualization

Though multiple data points are available for a project, data is still displayed as text on the web interface. Having interactive graphs and charts enhances the presentation of projects, and helps investors and receivers better understand the status of a project. 

This should also focus on the teller dashboard since most of the data from the teller is statistical and might be difficult to grasp for a receiver. The investor dashboard should have graphs related to net returns, net amount invested in projects, etc. The developer dashboard could have information on the status of the teller, total energy generated and have provisions to download detailed logs.

Data visualisation can be done with the help of libraries like D3.js or charts.js. More powerful tools that enable the creation of dashboards can also be embedded. This library would ideally have its own backend, anc communicate with the platform's backend separately. The handlers for internal communication should be authenticated JSON-RPC endpoints.

## Desktop and Mobile Apps

Opensolar can have desktop and mobile apps that communicate with the backend and serve critical functions like checking balance, monitoring paybacks, investing in projects. These apps reduce trust placed in the web interface since they are user run. It also helps expand the user base of the platform since entities are no longer required to use the web interface.

Mobile Apps open up potential for mobile device notifications which can be used to alert receivers to add stablecoin to their account, alert investors on their investment, etc. Mobile Tellers are also an interesting possibility to explore.

## Developer Engine

The developer engine is a core piece of openx's infrastructure. The DE enables entities to define various parameters for a project, and get feedback from the receivers through the platform. The DE will be responsible for:

1. **Originators** creating projects in stage 0
2. **Contractors** bidding for projects in stage 2
3. **Developers** installing the project in stage 5

The developer engine can be thought of as an editable web interface that would perform a set of defined functions. It bears close parallels and would eventually communicate with the CMS system described in the "Content Management System" section.

The developer engine should closely work with the backend to communicate project requirements, and should have a clean interface that enables developers to communicate their needs and suggestions.

## Entity Leaderboard

The platform could have a leaderboard where the investors that have invested the most are ranked in descending order. A similar leaderboard could be in place for recipients who can be ranked based on their rating or their number of completed projects.

The leaderboard can be further divided into classes \(Gold, Silver, Bronze, etc\) and this class can be displayed on the profile page of an entity. More awards like "Investor of the month" and similar can be added as necessary.

## Featured Projects

Currently, there is only one kind of project on the platform. There are two ideas linked to featured platforms:

1. Featured platforms are static and can be projects that are hosted at the DCI, projects that pay for the featured platform tag, etc
2. Featured platforms can change daily \(similar to "Quote of the Day" on quote websites\). These platforms would be curated by a list of content admins.

Featuring projects helps increase the amount of investment they receive and can generate more goodwill / advertisement for the project.

Projects could further be split into other categories like Sponsored projects, Advertised projects, etc. These present interesting sources of revenue for the platform.

## Filter System

Currently the filter system in the explore page is rudimentary and does not serve its intended purpose. An improved filter system which can filter on price range, location, rating, category similar to Amazon would benefit investors.

## Improved Company Account Handling

In the current architecture, a user's public key is shared with the company they represent. Different companies associated with different entiites \(investors, recipient, entities, etc\) should have the ability to have their own public keys and process hteir own funds.

Another improvement to this would be in-platform access control where company representatives can invite others to handle specific parts of the platform. This would require the building of an in-platform interface for access control \(which could probably be done when doing the CMS\).

## Inbuilt REC / Switch Integration

Currently, users have to navigate to a different portal to be able to view their RECs. Calling Swytch's APIs or by  having an ifram on Opensolar which links to Swytch can help make the UX of interacting with RECs better.

Another approach is to fork Swytch or create an in-house REC that is automatically credited to receivers based on Teller data.

## Interactive Search

The platform currently does not have search functionality. This makes it difficult for investors to find projects they are interested in without having to scroll through all projects on the explore page. An intereactive search similar to Airbnb/Booking.com with the following functionality:

1. Search by name
2. Search by location
3. Search by project type
4. Search by entity name

would be extremely useful for investors looking through projects on the platform.

## Investing Recommendations

Kickstarter routinely sends out marketing emails containing information like "Projects that you may find interesting", "Projects based on your funding history", etc. This would be nice to have for opensolar either as emails, or as notifications built into the platform since this would drive investors to checkout new projects. Recipients also get more direct exposure since the emails / notifications reach investors directly.

## Legal contract templates

Projects on Opensolar require legal contracts to be signed between different entities like the receiver and developer, the investor and the platform, etc. These contracts are stored on IPFS, and their hashes are stored in the "Stage Data" field associated with each stage. Having templates for legal contracts on the frontend \(eg. a docusign iframe\) makes this process easier, and the platform can store relevant data without much user intervention.

This enables faster processing of documents, and legal entities can register on the platform and provide these services directly. Having a central repo of contract templates also enables other platforms to borrow and adapt these to their application, saving them time and money associated with the legal process.

This would require the use of an existing digital signing application like DocuSign to be embedded within the platform, and the addition of functionality that enables users to sign documents, add new documents, etc. Once signed, documents must be stored on IPFS and the hashes stored as part of a project's details in order for them to be retrievable by other entities.

## Live ticker prices

Before investing, users will most certainly check the prices of the currency they are investing in. Having a ticker list from all major exchanges reduces clicks for the user and reduces potential for mistakes \(viewing coinbse.com which may have malicious prices instead of coinbase.com\).

A ticker can also be present on the recipient and developer dashboard so they can know how much their deposits and payments are worth.

## Local Projects

We should have a screen where we can display projects close to the user by asking for GPS permission. This would enable people to support local projects and invest in them. Similar to Airbnb, there could also be a "Projects Near You" section which displays this information.

## News / Educational Section

Opensolar can have a news / educational section where snippets on climate change articles, climate change statistics, etc can be presented and users can be informed about the latest research going on in the climate change arena.

The educational section can have quizzes, puzzles, short videos, etc where climate change basics can be explained in a concise manner.

## Openx Web UI

Openx does not have a web interface of its own. Having one would make operating openx accounts much easier and more efficient. Users can be presented with the number of platforms they are logged in, the number of platforms on which they have invested and more information.

An openx web UI would also enable the easy construction of a cross openx OAuth login 

## Project Updates Section

The project details page right now is quite static with little information apart from the stage and amoun raised being updated after the project has completed funding. A section titled "Project Updates" where the receiver updates investors on the status of the project, how things are progressing, etc on a weekly basis would be nice to have for investors to know that the project is progressing as expected.

Project Updates combined with Project Goals could be very informative for investors to study the progress of a project. It is also useful to display this in hindsight to potential recipients to show how the platform works. Project updates could also be sent to all entities who have invested in a project s o they know the progress associated with their investment.

## Public Pages for Entities

When an investors looks to invest in a project, they would ideally explore mulitple facotrs before putting in their money. A part of this includes background checks on the receivers and developers, and public pages might help with that.

Public pages for entities can be thought of similar to Facebook's profile page where an entity can describe themselves, add pictures of the themselves and the project, etc. This enables investors to better judge the platform's viability and the receiver's potential to pay back towards a project. It also reduces the probability of fake projects on the platform since investors would be vary of investing in projects that do not have a public page for the receiver.

The public page could support a variety of features like adding images, videos, text descriptions ,etc. It is important to note that we don't want to enable social media features like likes since the public page is meant to be purely informative.

Public pages can also be linked on other websites \(like facebook / twitter\) and clicking on these would redirect to the openx/solar profile of the entity. This feature could even be expanded to projects.

## Rescuer Web Interface

Currently, the rescuer is a CLI tool which can be used to sweep platform funds. The rescuer must have a neat web interface which performs the same functions so admins can visit the web interface and perform actions. This web interface can be deployed on a separate server and domain so it is accessible to admins at all times. Alternately, the rescuer can be part of the admin dashboard UI on openx.solar although this would not cover the event in which the openx.solar server goes down.

The rescuer could also come pre-loaded with the platform's seed but available only to those who have access to the platform' servers. This is not a security issue sicne they can access the platform's seed anyway. A pre-loaded platform can have options to trigger a sweep from the CLI so admins don't have to wait for the interface to load \(after  connecting with Horizon\)

## Project Map

A map which displays listings on Opensolar all over the globe is a great feature to showcase on the landing page of the platform. The UI could be imagined similar to Booking.com or Google Hotels where each project has an identifier \(could be minimum investment, potential impact, rating of investment, etc\).

A map helps people quickly navigate to a location of their choice and make faster investment decisions since the quick view option shows them details of the project they are interested in.

## VR/AR Model

A completed project can be depicted as a VR/AR model and entities can explore how their completed project would look in real time. This could be done using libraries in JS or could be done with advanced 3D rendering hardware like Oculus.

# Data visualization on the frontend

Though multiple data points are available for a project, data is still displayed as text on the web interface. Having interactive graphs and charts enhances the presentation of projects, and helps investors and receivers better understand the status of a project. This should also focus on the teller dashboard since most of the data from the teller is statistical and might be difficult to grasp for a receiver. The investor dashboard should have graphs related to the net returns, net amount invested in projects, etc. The developer dashboard could have information on the status of the teller, the energy generated and have provisions to download detailed logs.