Bench Development Configuration
===============================

This is the user configuration for a [Bench](http://mastersign.github.io/bench)
environment to build the Bench system itself and its documentation.

Use this repository as the source for the user configuration,
in case you check out the [Bench repository](https://github.com/mastersign/bench)
and initialize the configuration.

## Prerequisites for Building Bench

The usual way:

* [Microsoft Visual Studio &ge; 2015][VS] (e.g. Community Edition)
* if VS &ge; 2017: [Microsoft Build Tools 2015][MSBuild2015]
* [Sandcastle Help File Builder][SHFB] with VS integration

Without Visual Studio, e.g. for building on a server:

* [Microsoft .NET Framework &ge; 4.5 SDK][.NET-SDK]
* [Microsoft Build Tools 2015][MSBuild2015]
* [Sandcastle Help File Builder][SHFB]

## Setting Up the Bench Project

You need [Git][] already setup on your system.
If Git is available in the PowerShell, you can clone, build and initialize
the Bench project directory with the following lines:

```ps1
# clone the Bench project
git clone -b dev https://github.com/mastersign/bench.git ".\bench dev"
cd ".\bench dev"

# clone this development configuration
git clone https://github.com/mastersign/bench-dev-config.git ".\config"

# clone the app libraries
git clone https://github.com/mastersign/bench-apps-core.git .\applibs\core
git clone https://github.com/mastersign/bench-apps-default.git .\applibs\default

# load the app libraries into the Bench environment
robocopy .\applibs .\libs\applibs /MIR /XD .git /NJH /NJS

# build Bench in debug mode
build\build-debug.ps1

# initialize the Bench environment
auto\bin\bench.exe -v m i
```

## Building the Bench Documentation

After running `build\build-docs.ps1`, the complete documentation should be build in `docs\public`.

## License

This project is released under the MIT license.

Copyright © by Tobias Kiertscher <dev@mastersign.de>.

[Git]: https://git-scm.com/
[.NET-SDK]: https://www.microsoft.com/en-US/download/details.aspx?id=42637
[MSBuild2015]: https://www.microsoft.com/en-us/download/details.aspx?id=48159
[VS]: https://www.visualstudio.com/de/
[SHFB]: https://github.com/EWSoftware/SHFB/releases