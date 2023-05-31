# M3: Unity UAL
### Tasks:

-   UI Integration (Unity GUI and UiToolkit)
    -   Integration for Unity UI can be found [here](https://github.com/liquiidio/AnchorLinkTransportSharp/tree/unity_develop/Src/Transports/Canvas), [here](https://github.com/liquiidio/UniversalAuthenticatorLibraryUnity/tree/unity_develop/Src/Canvas) and in the Examples [here](https://liquiidio.gitbook.io/unity-plugin-suite)
    -   Integration for UiToolkit can be found [here](https://github.com/liquiidio/AnchorLinkTransportSharp/tree/unity_develop/Src/Transports/UiToolkit), [here](https://github.com/liquiidio/UniversalAuthenticatorLibraryUnity/tree/unity_develop/Src/UiToolkit) and in the Examples [here](https://liquiidio.gitbook.io/unity-plugin-suite)
-   Other
	- Necessary Interfaces and classes allowing integration of additional Wallets/Signature-Providers have been developed (See [here](https://github.com/liquiidio/AnchorLinkSharp/blob/unity_develop/AnchorLinkSharp/AnchorLink.cs#L25)) allowing configuration of individual Providers (depending on their implementation). Due to the Design automatic configuration via preprocessor-defines is not needed.
	- SignatureProviders for Anchor and Cloud Wallet have been developed (See [here](https://github.com/liquiidio/UniversalAuthenticatorLibraryUnity/tree/unity_develop/Src/Authenticators/WaxCloudWallet) and [here](https://github.com/liquiidio/UniversalAuthenticatorLibraryUnity/tree/unity_develop/Src/Authenticators/Anchor))
    -   Implementation allows Storage/Caching of last used Provider and Accounts
-   Multi Platform support
    -   Platform-/Build-Target-Incompatibilities have been removed (mostly Websocket-Connections and usage of the async-await/Tasking-API).
The Package works on the typically used Platforms (Windows, Mac, Linux, iOS, Android, WebGL) with differen LTS Versions of Unity3D.

## Additional
Examples can be found [here](https://github.com/liquiidio/UniversalAuthenticatorLibraryUnity/tree/unity_develop/Src/Authenticators/Anchor) and [here](https://drive.google.com/drive/folders/1hUU2inw5JppKDC0SsmMU9zENlrV8QaKE?usp=share_link) 

