# M4: Plugins Suite General

## Tasks:

-   General Bugfixing & Update to latest Versions
	*- Bugs have been fixed and Packages have been aligned with latest Versions*    
-   Additional Unittests, Update of Unittests
	*- Additional Unittests have been added and are matching the latest Versions of the integrated Service*
-   Documentation, README-files, API-Docs, Installation instructions
	*- Source Code Documentation and README-files have been extended*
-   Multi Platform support
	*- Platform-/Build-Target-Incompatibilities have been removed (mostly Websocket-Connections and usage of the async-await/Tasking-API BUT ALSO the HttpClient used in WebGL and other Targets).
The Packages work on the typically used Platforms (Windows, Mac, Linux, iOS, Android, WebGL) with differen LTS Versions of Unity3D.*

## Additional
- Examples of succesfully running Pipelines (including UnitTests, Releases, Packaging etc.) can be found [here](https://github.com/liquiidio/HyperionApiClient/actions/runs/4298089809), [here](https://github.com/liquiidio/AtomicAssetsApiClient/actions/runs/4167151869) and [here](https://github.com/liquiidio/AtomicMarketApiClient/actions/runs/4653309053). Packages requiring User-interaction are excluded from Unittests as they can't run automatically without interaction.
- The HttpClient implementation for WebGL compatibility can be found [here](https://github.com/liquiidio/AtomicMarketApiClient/tree/unity_develop/Src/AtomicMarketApiClient) , [here](https://github.com/liquiidio/AtomicAssetsApiClient/tree/unity_develop/Src/AtomicAssetsApiClient) and [here](https://github.com/liquiidio/HyperionApiClient/tree/unity_develop/Src/HyperionApiClient) (everything starting with Http in the name)
- Releases, Packages and Pipelines can be found in the individual [repositories](https://github.com/orgs/liquiidio/repositories)

*Note: In the meantime we have removed some of the tests from the pipelines as they are often failing due to rate-limits on public APIs.*
