# Unity Plugin Suite


The following is a proposal to complete the Unity Plugin Suite with subsequent publication in the Unity Asset Store. 

## Liquiid

Liquiid develops software solutions and offers consulting in the area of decentralized gaming with a focus on Antelope-based blockchains, specifically WAX.

Liquiid develops own games based on Antelope as well as open source plugins/tools/SDKs to enable the use and integration of antelope-based blockchains in games and to simplify the integration and use of decentralized technology for game developers.


## Functional Scope & Objective

The Unity Plugin Suite provides a complete set of all required plugins and tools for the integration of various available services and allows Unity developers to create blockchain-based games based with free choice between available and commonly used services.

A full implementation/integration of all interfaces, 3d party solutions and protocols known and widely used from other platforms is essential to provide Unity developers with the same functionality and richness of tools, plugins and libraries while maintaining the same user and developer experience known from other platforms.

## Professionality & Quality Measurements

Alongside price and brand loyalty, quality standards for products or services are decision making criteria in customer acquisition and customer loyalty. Adherence to and promotion of quality standards often serves as a unique selling proposition and represents a competitive advantage. In addition to the image of a product or service, quality can also influence the reputation of the brand and the company - positive as well as negative (negative example: missing documentation, no unit tests, poor code coverage).

Quality standards promote customer confidence but also productivity with regard to maintainability, further development and efficiency.

In order to provide developers with high-quality solutions and to make it as easy as possible for them to start development or extension of Antelope-based games as efficiently as possible in a trustful environment, the following quality standards have to be met.


## M1: Anchor & ESR Unity Integration

A native integration compatible with Unity3D and C# allowing users and developers to connect and communicate with Anchor Wallet and ESR-based applications. The Anchor & ESR Integration consists of multiple libraries for the ESR-Protocol, the Anchor-integration, Transports etc. which will be included via Submodules while being packaged and published as a single Package. 

#### Objective
A native implementation without the use of WebViews or Javascript engines. Compatibility with Windows, Mac, Linux, WebGl, iOS, Android must be guaranteed. Consoles are currently excluded, special SDKs from Unity are needed which can be obtained via the verified Partners Program.
  

### Current State

The Anchor & ESR Unity Integration is already under Development. We re-engineered the original Projects by Greymass to allow a native implementation as close to the original typescript-implementation as possible, as this  allows simplified maintenance and extension. 
  

### Tasks

- General Bugfixing

	- Solving the issues behind the last 4 failing UnitTests. (Only 13 of 17 UnitTests are passing.)

- Maintainability/Code Streamlining

	- Removing code debt, streamlining code, improving maintainability and development capabilities.
- Addition of currently missing functionality
- EosSharp Integration
	- Seamless integration with EosSharp via the ISignatureProvider-Interface and the AbiSerializationProvider-Class (it's very loosely integrated which needs to be improved)

- UI Integration (Ui-Frameworks Unity GUI and UiToolkit - covers only reengineering of standard Views used by Anchor)
	- Visualizations/UI integration for Unity UI (old but commonly used UI-Framework)
	- Visualizations/UI integration for the newer UiToolkit
- Transports and Storage
	- implementation of a UnityTransport (if necessary multiple Transports for different Build Targets)
	- Implementation of a UnityStorageProvider (likely PlayerPrefs)
- Multi Platform support
	- Manual Builds and tests for each of the Build Targets (Windows, Mac, Linux, iOS, Android, WebGL) and different latest LTS Version of Unity
	- Adaptations due to platform-specific requirements
- Wrapping of the individual Components into a single package in reasonable way

***Duration - 1 Month***
***(4 FTE - Total: 40k USD)*** 

  

## M2: WCW Unity Integration

***Additional Research and Input from WAX needed!***

#### General:

As the WCW is based on OAuth, a well-designed Plugin should allow an implementation where opening a WebView is only needed once. As OAuth is used ,only the OAuth-Token should be needed to communicate and authenticate with the WCW-API and therefore only the Login followed by a callback to a local HttpListener (instead of a Browser-callback) should be needed to get the OAuth-Token into the Application.

***Info on the WCW-API, OAuth etc. needed***  

An integration based on one of the Open-Source and free WebView-Plugins is the only thing making sense. Unfortunately there's no good support for WebViews in Unity and the available Plugins come with some drawbacks and integration is complex. 

Technically, without having any detailled information, the planned approach is to make use of a combination of local HttpListeners receiving OAuth-Callbacks from WCW-related web-adresses opened through the WebView-Plugin, gathering necessary initial information like OAuth-Tokens, followed by regular non-browser-based (no WebView needed) communication with the WCW-API/Server. 

- https://github.com/Voltstro-Studios/UnityWebBrowser

- https://github.com/gree/unity-webview (preferred due to platform-support)

####  Tasks
- Familiarization with the architecture and low-level technical interaction scheme with the Wax Cloud Wallet.
- Research possible implementation paths with the goal of an implemention with as little WebView-interactions as possible.
- If necessary, discussion of suggestions for improvements of the WCW in close contact with WAX in order to ensure the most seamless UX possible.
- Research and prototype test-versions based on the two open source WebViews to be able to make best possible choices.
- Tight integration with EosSharp (through implemenation of the ISignatureProvider-Interface etc.) resulting in sustainable integration with the UAL.
- Multi Platform support
	- Manual Builds and tests for each of the Build Targets (Windows, Mac, Linux, iOS, Android, WebGL) and different latest LTS Version of Unity
	- Adaptations due to platform-specific requirements

***Duration - 2 Months***
***(4 FTE - Total: 40k USD)***

  

## M3: Unity UAL

Development of a native UAL allowing the use of supported SignatureProviders, similar to the js-based UAL allowing developers and users the same interaction flow and UI/UX on all different platforms. Priority here is User and Developer Experience while building the same base with extension-capabilities allowing to support additional SignatureProviders like Wombat, MetaMask, AIKON, other Wallets or SideChain-Auth in the future.

### Tasks:
- UI Integration (Ui-Frameworks Unity GUI and UiToolkit - covers only reengineering of standard UAL Views)
	- Visualizations/UI integration for Unity UI (old but commonly used UI-Framework)
	- Visualizations/UI integration for the newer UiToolkit
- Other
	- Interface-Specification to allow integration of other SignatureProviders
	- Generic and dynamic way to configure SignatureProviders and their Visualization within the UI
	- Integration, Support of currently available SignatureProviders (Anchor and WCW)
	- Automatic configuration based on preprocessor-defines within packages added (UAL will then only allow specific Providers if the necessary Packages are installed)
	- Storage/Caching of last used Provider and Accounts
- Multi Platform support
	- Manual Builds and tests for each of the Build Targets (Windows, Mac, Linux, iOS, Android, WebGL) and different latest LTS Version of Unity
	- Adaptations due to platform-specific requirements

_Note: Special attention must be paid to the exact usage of WebSockets as WebSockets are not natively supported on certain platforms (WebGL) and the usage of multiple parallel WebSocket-connections is only possible under consideration of certain requirements. (Communication with Anchor and Scatter is Websocket-based)_

***Duration - 1 Month***
***(2 FTE - Total: 20k USD)***

  
  

## M4: Plugins Suite General

#### Objective
The individual Plugins/Packages/SDKs of the Suite are already mostly developed but havn't been actively maintained over the last 6-12 months, bugs are present in some cases. Additional working time must be invested to bring them up to date. Also the documentation is partly incomplete and needs to be completed, README files should have consistent format and contain installation instructions and links to API docs and 3D-party-services.

#### Tasks:

- General Bugfixing

- Update to latest Versions

- Additional Unittests, Update of Unittests to match the latest Versions

- Extending the documentation in the source code (annotations used to generate the gitbooks)
- Extension of README-files with links to Project, API-Docs, installation instructions
- additional basic usage examples
- Multi Platform support
	- Manual Builds and tests for each of the Build Targets (Windows, Mac, Linux, iOS, Android, WebGL) and different latest LTS Version of Unity
	- Adaptations due to platform-specific requirements

#### Plugins/Packages/SDKs:
*Following list of Plugins/Packages/SDKs are included in the scope of this proposal:*

- AtomicAssetsApiClient

- AtomicMarketApiClient

- HyperionApiClient

- Anchor/ESR Integration

- EosSharp

- EosWsSharpClient

- WCW Unity Integration

- UAL

*Following Plugins/Packages/SDKs are not included in this proposal*
- HyperionStreamingClient: 
	- The current version of the SocketIO-based Streaming-Api will be replaced with a new streaming-Api in the upcoming months. Therefore maintainenance or further development of the Streaming-Client doesn't make sense.
- DfuseClients (Queries/Subscriptions): 
	- As EosNation (and Pinax Network - EosNations TheGraph & Firehose hosting Company) is a huge supporter of TheGraph, Firehose and Substreams and they want to switch their entire stack from dfuse to TheGraph-based APIs while stopping to further develop dfuse, it seems to be likely that EosNation will switch off dfuse within the coming months and will instead offer only the firehose-service. Therefore maintainenance or further development of the dfuse-Clients doesn't make sense.

***Duration - 1 Month***
***(1 FTE - Total: 10k USD)***

  

## M5: CI/CD, Unittests/Documentation/Packaging


#### Objective
CI/CD pipelines to ensure high quality software distribution and reliable deployment of code changes and packages as well as automation of recurring tasks and the increase of the professionalism level as well as the maintainability as a distinguishing feature and sales argument including automatic testing and generation of online and offline documentation.


#### UnitTests
For quality assurance, unit tests are implemented per project/package and pipelines are created for automatic execution in case of internal changes and for manual execution if required. The UnitTests check core functionality and compatibility of the package with the interacted service (e.g. AtomicAssets or AtomicMarket API, WAX Cloud Wallet) as well as internal functionality (e.g., serialization, deserialization, persistence, conversions, etc.),
but not compatibility with single specific Unity versions or build targets due to the high, non-cost effective effort.

Recently successfully and bug-free executed unit tests are usually an indicator of high quality and visualize to developers who plan to use of a library, its timeliness, flawlessness, professionalism, and more.

In addition, the use of unit tests and CI/CD pipelines allows for regular verification of compatibility with external services as well as facilitated maintainability.


#### UnityPackages
In order to provide unity packages to developers as quickly as possible, to increase the professionalism of projects as well as their reach and to reach the preferences of individual developers, unitypackages will be provided
- via the Unity Package Manager via the Git URL
- via OpenUPM
- via the Unity Asset Store

The automatic creation and release of packages through CI/CD pipelines after a code update assures the developer that the latest release contains the latest code changes and allows developers to easily update to the latest versions.

Example: https://github.com/Cysharp/UniTask#upm-package


#### Online and Offline Documentation
In order to continuously provide up-to-date documentation of the projects with the packages, pipelines for the automatic generation of both 
- online documentation in the repository via Github Pages and GitBook or DocFx
- offline/PDF documentation included in the Package
will be implemented. The online documentation allows referencing of the documentation by third parties like Pink.gg (in contact), WAX or other Developers as well as merging of multiple sources into one overall documentation in the future.

The integration and shipping of offline/PDF documentation with the respective packages is common, increases professionalism level and allows the developer to view the documentation of the local version of a package without searching for appropriate online resources.


#### Additional Documentation
In the documentation mentioned here we focus mainly on documentation of packages and their functionality and usage, only installation instructions, documentation about namespaces, classes, methods and members as well as minimal usage examples are integrated and generated.

The documentation will be extended independently from this proposal with tutorials, best practices and extended usage in the coming months after the completion of the plugin suite after we have received feedback and questions from users. (as liquiud is able to receive Guild-points in the ratings a continuous extension of the documentation makes sense) Currently, no further labs-proposal is planned for this.

#### Tasks

- implementation and setup of Pipelines to run UnitTests for the different Plugins/SDKs/Tools

- implementation and setup of pipelines allowing to automtically build, extract and deploy the individual packages as unitypackages downloadable via OpenUPM and Git-URL (later also provided via the AssetStore)

- implementation and setup of Pipelines allowing to generate a GitBook- or DocFX- documentation from annotated code followed by publishing them to the github pages of the repository
  
***Duration - 1 Month***
***(2 FTE - Total: 20k USD)***
  

## M6: Unity Asset Store

### General
According to the current state of knowledge, it seems that only security-critical solutions must be subjected to the security audit offered by Unity and it's Verified Solutions Partners Program.

It can therefore be assumed that plugins/libraries/tools that use 3-party services such as AtomicAssets, AtomicMarket, Hyperion or Dfuse in a read-only manner do not need to go through the audit to enable publishing on the Unity Asset Store. This should limit both the time and cost required for audits.

The Anchor/ESR and Wax cloud wallet integrations, however, must pass the audit securely.

### Publishing Pattern 
In order to promote visibility and branding with little effort and occupy a large space in the Unity Asset Store the following approach to publishing is suggested.

#### Individual Packages
The individual packages are each published individually as packages in the Unity Asset Store under a meaningful name (consisting of the original name plus suffixes and prefixes such as "Unity", "Client", etc.).

#### Packs, Suites, SDKs
Additionally, all packages will be published together in a "WAX Blockchain SDK" package which contains all packages and allows the user both selective as well as complete installation/import of the individual packages.

In addition, it is intended to release further "WAX Packages" like
- "WAX Blockchain NFT SDK" containing WCW integration, Anchor, UAL, AtomicAssets
- "WAX Blockchain History" containing Hyperion and possibly dfuse.
- "WAX Blockchain Markets SDK" including AtomicAssets and AtomicMarket or similar.
- " WAX UiToolkit SDK" and "WAX Unity UI SDK" to cover the different UI-Frameworks
- ... 

to create and publish blockchains that are simply composed of an individual composition of the already provided packages as these could be published with little effort without additional audits.

*Note:* As the setup of additional Suites/Packs (Compositions of other Packages) is quite simple and quickly done we are open for any ideas. In addition we would like to extend the number of Packages as well as Suites in the future to allow for even better visibilty and reach. 

#### Objective
The objective is to provide a high number of packages with specific keywords such as "NFT/NFTs" or "blockchain" in name as well as description as this results in crowding out other packages and highlighting WAX SDKs among other "Blockchain" or "NFT" SDKs.

In addition, a high number of solutions in the enterprise space (some with a "Verified Solution" tag) increases Confidence and signals to the developer a high feature set, full ecosystem coverage, and professionalism and allows WAX to stand out from other competitors. 

Moreover, it allows the extension of the Suite with additional integrations as individual packages while providing additional multi-package SDKs focused on specific keywords and trends, increasing the general portfolio of available Developer-Tooling.

Also, individual Packages and Packs/Suites/SDKs can be marketed in seperate or as a whole allowing much diversified Mutli-Step Marketing, focusing on specific topics or trends.

Packages and Packs/Suites/SDKs will be provided free of charge.


*Note: Wrapping individual smaller Packages into Packs or Suites of Packages containing a group of tools relating to specific functionallity is a common approach on the Unity Asset Store and a widely used publishing pattern.*

#### Tasks
- Communication with Unity and the Unity Verified Partners Program
- Application in the Unity Verified Partners Program to be able to go through Audit Processes
- Audit Process for Packages where Audits are needed
- if necessary, adaptation to security guidelines, elimination of issues
- Setup, publication of all the different Packages on the Unity Asset Store

***Duration - 1 Month***
***(1 FTE - Total: 10k USD)*** *Covering only the working time, Audit Fees or Verified Partners Application Fee have to be covered by WAX.*


# Roadmap

1. M1 and M2 in parallel, with highest Priority.
2. Release of Open Source and licensed code available for use but temporarily without the right of redistribution or modification etc. . *(Due to the current situation with the copyright infringement and the lawsuit we want to make sure that the developed code is not modified or redistributed before all tasks have been executed and the Packages have  been published on the Asset Store.)*
3. Application in the Unity Verified Partners Program + Security Audits for Anchor/ESR and WCW. Costs for Security Audits and application in the Verified Partners Program have to be covered by WAX.
4. M3, M4, M5 in parallel (better Developer and User Experience as well as better extensibility (see above), increased reach etc. in parallel with development and setup of Pipelines + Update of existing Packages to match the latest versions).
5. Once Packages have passed the Audits and everything has been published on the Asset Store change of temporary license to MIT-license allowing anyone to copy, modify, redistribute etc. 

### WAX Exclusivity
- All Packs/Suites (compositions of multiple individual packages) under this propasal will remain WAX exclusive for one year (starting on the day of successful publication) while individual single Packages will keep their original name and do not get any additional branding as the services offered by these 3d parties are not WAX exclusive in any way and a WAX branded package-name would be misleading (Examples: AtomicAssetsClient, AtomicMarketClient, AnchorLinkSharp). 
- Liquiid will neither add Packs or Suites containing branding of other Blockchains or publicly advertise packages or packs contained in this proposal for other, non-WAX Blockchains for the same timeframe. 
- Due to the nature of these packages and services accessed provided on multiple blockchains, Developers on other Blockchains still have the ability to use these packages with non-WAX-blockchains. 

### Potential Blockers
- Missing WCW documentation
- Delay through the Unity Verified Partners Program

### Maintenance
Maintenance of Packages proposed is included for one year. No further maintenance poposals are made.

### Working Time and Total Requested Funds:
Planned Total duration: 3-5 months (if no external blockers like missing WCW-documentation appear)

_1FTE = 1Employee * 1Month of work = 10,000 USD_

- M1 - 4FTEs (40k USD)
- M2 - 4FTEs (40k USD)
- M3 - 2FTEs (20k USD)
- M4 - 1FTEs (10k USD)
- M5 - 2FTEs (20k USD)
- M6 - 1FTEs (10k USD)

**Total Requested Funds: 140k USD**
