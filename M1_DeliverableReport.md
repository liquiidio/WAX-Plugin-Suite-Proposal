
# M1: Anchor & ESR Unity Integration

## Tasks

 - General Bugfixing
	 *- Bugs have been fixed and the last failing UnitTests are completing successfully*
 - Maintainability/Code Streamlining
	 *- Code has been streamlined to increase maintainability (See Repositories)*
 - Addition of missing functionality
	 *- Missing functionality has been added (See Repositories, try the Packages functionality)*
 - EosSharp Integration
	 *- EosSharp has been seamlessly integrated while making use of the ISignatureProvider and AbiSerializationProvider-Classes (See XXX)* 
 - UI Integration
	 *- UI has been integrated for both UI-Frameworks (Unity UI, UiToolkit). The integrated and developed UI matches the UI of the typically used Anchor Transports (see XXX)*
 - Transports and Storage
	 *- Transports for both UI-Frameworks (Unity UI, UiToolkit) have been developed, UI/Visualization has been integrated (See above)*
 - Multi Platform Support
	 *- Platform-/Build-Target-Incompatibilities have been removed (mostly Websocket-Connections and usage of the async-await/Tasking-API).*
*The Package works on the typically used Platforms (Windows, Mac, Linux, iOS, Android, WebGL) with differen LTS Versions of Unity3D.* 

The 3 Packages (AnchorLinkSharp, AnchorLinkTransportSharp, EosioSigningRequest - aligned with the TypeScript-Version from Greymass) have been wrapped into a sinlge unitypackage and upm-branch (See XXX)


## Additional 
- An Example of a successfully running Pipeline (including Unittests, Builds, Releases etc.) can be found [here](https://github.com/liquiidio/AnchorLinkSharp/actions/runs/3940803603): 
- Release-Packages can be found in the Repo [here](https://github.com/liquiidio/AnchorLinkSharp) 
- Examples can be found [here](https://liquiidio.gitbook.io/unity-plugin-suite) and a small selection of Desktop-Builds [here](https://drive.google.com/drive/folders/1hUU2inw5JppKDC0SsmMU9zENlrV8QaKE?usp=sharing)
