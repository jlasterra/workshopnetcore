# Information

## Setup and installation:
* [.NET Core SDK](https://www.microsoft.com/net/download/core)
* [Visual Studio Code](https://code.visualstudio.com/) with C# extension 
* [Docker CE (edge version)](https://www.docker.com/community-edition#/download)
* Start docker and pull microsof/dotnet images with `./setup.sh` or `./setup.ps1`

Optional
* Windows10 machine with [Visual Studio 2017 CE](https://www.visualstudio.com/free-developer-offers/)
* [dotPeek](https://www.jetbrains.com/decompiler/)  
* [ILSpy](http://ilspy.net/)
* [Nuget Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)

## Get started with the dotnet CLI and the new SDK
* What is installed and where? Quick look at the dotnet core installation folder.
* [SDK architecture](https://docs.microsoft.com/en-us/dotnet/core/tools/cli-msbuild-architecture)
* Introduction to donet CLI basic commands and new SDK architecture based on msbuild targets 
    * `dotnet --info`
    * `dotnet --version`
    * `dotnet new`
    * `dotnet restore`
    * `dotnet run`

## Understanding the new Project.csproj
* [NuGet is now fully integrated into MSBuild](http://blog.nuget.org/20170316/NuGet-now-fully-integrated-into-MSBuild.html)
* [NuGet pack and restore as MSBuild targets](https://docs.microsoft.com/en-us/nuget/schema/msbuild-targets)
* [Packages, Metapackages and Frameworks](https://docs.microsoft.com/en-us/dotnet/core/packages)
* [Csproj props](https://docs.microsoft.com/en-us/dotnet/core/tools/project-json-to-csproj)
* `dotnet restore` and the autogenerated `project.assets.json` file.
* Manual trimming of the autogenerated dependency tree.
* Expanding the csproj file with `dotnet msbuild /pp:fullproject.xml`
* Understanding and modifying the SDK props and targets.

## Creating the VotingApp library using TDD
* Basic tips and tricks for using VSCode
    * [VSCode Windows Shortcuts](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
    * [VSCode Mac Shortcust](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)
* Use integrated terminal for running dotnet cli commands.
* Create xunit project
* Install and understand how the C# extension (aka as [Omnisharp](http://www.omnisharp.net/) project) works.
* Run and debug unit tests.
* Extend the dotnet cli tooling. 
    *  [DotNetTools](https://github.com/aspnet/DotNetTools) for live testing with `donet watch test`
* Create classlib project.
* Map the dotnet cli commands to your keyboard thanks to VSCode and [`tasks.json`](https://code.visualstudio.com/docs/editor/tasks)
* Use a [sln](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-sln) file for better project management.
* Checkpoint: `git clone --branch unit-test https://github.com/paulopez78/workshopnetcore.git`

## Creating the VotingApp Console Client (Windows machine required)
* Use the debugger and understand the `launch.json` file.
* [Target .net core and .net framework](https://docs.microsoft.com/en-us/dotnet/standard/frameworks)
* [Introducing .net standard](https://docs.microsoft.com/en-us/dotnet/standard/library)
    *   Reference assemblies
    *   Implementation assemblies
    *   Facade assemblies (aka [type forwarding](https://blogs.msdn.microsoft.com/davbr/2009/09/30/type-forwarding/))  
*  Target different frameworks in the context of the votinapp for better understanding of netstandard.
* [netstandard analogy](https://github.com/paulopez78/dotnet-target-frameworks)
* Checkpoint: `git clone --branch console-client https://github.com/paulopez78/workshopnetcore.git`

## Publishing the VotingApp Console in different frameworks and runtimes
*   [Portable vs Self contained deployment](https://docs.microsoft.com/en-us/dotnet/core/deploying/index)
*   [Runtime identifiers](https://docs.microsoft.com/en-us/dotnet/core/rid-catalog)
*   [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)
*   Use windows, macosx and docker (for linux runtime) for testing different published outputs.

## Creating the ASP.NET Core VotingApp.Api  
* [Swagger](https://github.com/domaindrivendev/Swashbuckle.AspNetCore)
*  Use the debugger and understand the `launch.json` file.
*  Using [static files](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/static-files) for building the UI.
*  Using websockets for realtime voting.

## Upgrading the VotingApp.Api to .NET Core 2.0 Preview 2
*   What's new in [.NET Core 2.0](https://www.microsoft.com/net/core/preview#windowscmd) ?
*   Pinning your SDK with `global.json` file
*   New netcoreapp2.0 and netstandard2.0 packages
    *   Introducing `netstandard.dll` reference assembly
    *   Reuse existing .net framework libs thanks to the `mscorlib.dll` facade assembly
*   [New ASP .NET Core All package and the storage folder](https://andrewlock.net/the-microsoft-aspnetcore-all-metapackage-is-huge-and-thats-awesome-thanks-to-the-net-core-runtime-store-2)
*   [New default builder and default configuration](https://andrewlock.net/exploring-program-and-startup-in-asp-net-core-2-preview1-2/)

## Running the VotingApp with Docker
*   What is a docker container and a docker image
*   Docker basic commands
    * `docker build`
    * `dotnet run`
*   [Dockerfile](https://docs.docker.com/engine/reference/builder/)
*   Official .NET Core Microsoft Images
    * [dotnet core images](https://hub.docker.com/r/microsoft/dotnet/)
    * [aspnet core build images](https://hub.docker.com/r/microsoft/aspnetcore-build/)
    * [aspnet core runtime images](https://hub.docker.com/r/microsoft/aspnetcore/)

## Building and Deploying the VotingApp with Docker Compose
*   [Docker compose](https://docs.docker.com/compose/) for development and continuous integration and deployment workflows.
*   [Multistage docker file for building runtime images](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)
*   Debugging with docker, vscode and .net core
*   Docker swarm, Docker Cloud and Docker for Azure.

## Refactoring towards EventSourcing, CQRS and microservices
*  [Sample voting app with eventsourcing architecture](https://github.com/paulopez78/votingapp)
*   Understanding event sourcing and CQRS concepts.
*   Creating projections of your events stream.
*   Using a helper [event sourcing](https://github.com/netcorebcn/easyeventsourcing) nuget package.

## File References
* [Voting Tests](https://github.com/paulopez78/workshopnetcore/blob/master/test/VotingApp.Tests/VotingTests.cs)
* [Voting Object](https://github.com/paulopez78/workshopnetcore/blob/master/src/VotingApp.Lib/Voting.cs)
* [Util targets](https://github.com/paulopez78/workshopnetcore/blob/master/tools/util.targets)
* [Console Client](https://github.com/paulopez78/workshopnetcore/blob/master/src/VotingApp.Client/Program.cs)
* [Voting Controller](https://github.com/paulopez78/workshopnetcore/blob/master/src/VotingApp.Api/VotingController.cs)
* [Tasks Json](https://github.com/paulopez78/workshopnetcore/blob/master/.vscode/tasks.json)
* [Launch Json](https://github.com/paulopez78/workshopnetcore/blob/master/.vscode/launch.json)

## More Awesome Resources
* <https://blogs.msdn.microsoft.com/dotnet/2014/12/04/introducing-net-core/>
* <https://blogs.msdn.microsoft.com/dotnet/2016/02/10/porting-to-net-core/>
* <https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/>
* <https://www.youtube.com/playlist?list=PLRAdsfhKI4OWx321A_pr-7HhRNk7wOLLY&app=desktop>
* <http://adamralph.com/netstandard-deck/>
* <https://andrewlock.net/understanding-net-core-netstandard-and-asp-net-core/>
* <https://github.com/davidfowl/NetStandard>
* <https://channel9.msdn.com/Shows/On-NET/Immo-Landwerth-Net-Standard>
* <https://channel9.msdn.com/Blogs/Seth-Juarez/What-is-NET-Standard>
* <https://channel9.msdn.com/Events/ASPNET-Events/ASPNET-Fall-Sessions/Class-Libraries>
* <https://channel9.msdn.com/Blogs/dotnet/CoreCLR-is-now-open-source-on-GitHub?ocid=player>
* <https://vimeo.com/213913286>
* <https://www.slideshare.net/citizenmatt/the-howdareyoucallmeanidiots-guide-to-the-net-standard-ndc-london-2017>
* <https://github.com/dotnet/standard/blob/master/docs/netstandard-20/packaging.md>