# M2: WCW Unity Integration

## Tasks

The initial plan was discarded after consultation and agreement with the WAX team and the following was implemented instead:

### WebGL Integration
Cloud Wallet has been natively integrated into Unity3D for the WebGL Build Target. The integration makes use of a custom "jslib" compiled to WebAssembly using emscripten while interacting with the Browser Scripting and the waxjs.js-library directly.

### Desktop Integrations
A temporary Solution was developed to integrate Cloud Wallet on Desktops (MAC, Linux, Windows). It's making use of a local HttpListener run by the Game Client and Callbacks between the Browser and the Client to call waxjs.js-functions and to communicate with the Cloud Wallet Server. It's not recommended to use this Solution in Prodduction as it comes with security risks but this Solution allows Developers to develop and test their Games directly on Desktops and within the Unity Editor without the need to build their Application for WebGL every time. 

### Mobile Integration
As interaction with mobile Browsers from Mobile Applications comes with limitations or is not permitted (no storage of Cookies, permanent warnings, Browser-incompatibilities, OAuth-specific challenges, complete forbiddance on iOS) in addition to the implementation described in "Desktop Integration" the Solution is making use of "SFSafariViewController" and "Chrome Custom Tabs" opening the website hosting waxjs in operating system specific secure Browser Environment while storing cookies.

### Cloud Wallet and waxjs.js updates
An update to the new Wax Cloud Wallet und waxjs.js including newly added functionallity (containing additional functionallity added in the new Cloud Wallet implementation) has been done after the initial development of the solution described above.

#### Outlook
A native integration for all platforms will follow after the cloud wallet functionality has been extended by Liquiid or another team commissioned by WAX with the implementation.

## Additional
- WAX has tested the integration with partners and Liquiid has fixed bugs
- Source Code and Releases can be found [here](https://github.com/liquiidio/CloudWalletUnity)
- Examples, Builds and Documentation can be found [here](https://liquiidio.gitbook.io/unity-plugin-suite) and [here](https://drive.google.com/drive/folders/1hUU2inw5JppKDC0SsmMU9zENlrV8QaKE?usp=share_link) 

## Charges
Due to the above changes (resulting in less work) and the integration of the new cloud wallet (resulting in more work), the effort has been slightly reduced and **we propose a price change from 40k USD to 30k USD for this milestone**.
