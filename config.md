# User Configuration

## Environment

With the following properties, you can control the composition of the environment variables and the isolation level of the Bench environment from the Windows system.

* OverrideHome: `true`
* OverrideTemp: `true`
* IgnoreSystemPath: `true`
* UseRegistryIsolation: `true`
* RegisterInUserProfile: `false`
<!-- * EnvironmentPath: `$HomeDir$\bin` -->
<!--
* Environment:
    + `MY_VAR`: `my custom value`
-->

## Machine Architecture

With the following property, you allow the usage of 64Bit binaries.
Set this property to `true` if you intend to use this Bench environment
only on systems which support 64Bit code.

* Allow64Bit: `true`

## App Libraries

With the following dictionary property, you can add additional app libraries.

* AppLibs:
    + `core`: `$BenchRoot$/applibs/core`
    + `default`: `$BenchRoot$/applibs/default`

## Quick Access

With the following properties, you can control the appearance of the launchers for the three shells.

* QuickAccessCmd: `true`
* QuickAccessPowerShell: `true`
* QuickAccessBash: `true`

## Dashboard

With the following properties, you can control certain behavior of the Bench Dashboard.

* AutoUpdateCheck: `true`
* DashboardSetupAppListColumns: `Order`, `Category`, `Label`, `Version`, `Active`, `Deactivated`, `Status`, `Typ`, `License`, `Comment`

## Project Archive

With the following properties, you can control the project archive.

* ~~ProjectArchiveFormat: `7z`~~
* ProjectArchiveDir: `archive`

## Properties Added by the CLI

If the Bench CLI sets properties, which are not already listed in this file,
it appends them to the end of the file.
