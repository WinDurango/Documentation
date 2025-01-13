# Setup

## Prerequisites

### To launch
1. [Developer Mode enabled](#enabling-developer-mode)
2. Windows 10 (or later)
3. Windows App SDK (if debugging)
4. Visual Studio 2022 OR WinDbg (for debugging if needed)
5. Visual C++ Redistributables (unsure which are needed)
6. Graphics Tools (from `Settings > Apps > Optional Features` (Windows 10) or `Settings > System > Optional Features` (Windows 11))
7. The latest [release](https://github.com/WinDurango/WinDurango/releases)/[artifact](https://github.com/WinDurango/WinDurango/actions/workflows/msbuild.yml)

### To build

1. Everything from [the launch requirements](#to-launch) (except for the release/artifact)
2. Windows 10 (or later)
3. Windows App SDK
4. Visual Studio 2022
5. Git
6. Windows 11 SDK version 10.0.17134.0 or later
7. The following from the Visual Studio Installer
   - Desktop Development with C++
   - Windows Application Development
   - MSVC (143) C++ Build Tools
   - C++ (143) Universal Windows Platform Tools
   - .NET Desktop Development
   - Game Development with C++
8. The project cloned to a folder

## Running the package

To run the package, you need to setup the [Launch prerequisites](#to-launch) and have already [registered the package](#registering-the-uwp-package).   
You'll need to also copy in all the DLLs from the latest [release](https://github.com/WinDurango/WinDurango/releases)/[artifact](https://github.com/WinDurango/WinDurango/actions/workflows/msbuild.yml) into your app's Mount folder (the folder that has the EXE).  

After that, you just need to open the app through the start menu. (or other preferred way of running UWP apps)

## Registering the UWP package

You cannot normally run a UWP app's EXE file directly, instead you have to register the UWP app and launch it from the Start Menu/a Debugger.

1. [Enable Developer Mode](#enabling-developer-mode)
2. Go to the Mount folder of your game (where the EXE sits)
3. Open Powershell.exe to that directory
4. Run `Add-AppXPackage -Register .\AppxManifest.xml`

## Enabling Developer Mode

To register UWP apps, you have to enable Developer Mode.

1. Go to For Developers in Settings (path differs depending on Windows version, read below)
   - Settings > Windows Update > For Developers (Windows 10)
   - Settings > System > For Developers (Windows 11)
2. Enable Developer Mode

# Building

1. Clone the repo  
   - `git clone --recursive https://github.com/WinDurango/WinDurango.git`


2. Open the project solution in Visual Studio   
   - If you get a message asking about upgrading projects, press continue.

TODO: DO THE REST SINCE THIS CHANGED LOTS

3. [Generate](#generating-idls-from-winmds) and copy the following IDLs into `/dlls/winrt_x/External`
   - Windows.Xbox.ApplicationModel.State.idl (656kB)
   - Windows.Xbox.ApplicationModel.State.Internal.idl (33,379kB)
   - Windows.Xbox.ApplicationModel.Store.idl (10,655kB)
   - Windows.Xbox.idl (3,316kB)
   - Windows.Xbox.Input.idl (53,430kB)
   - Windows.Xbox.Management.Deployment.idl (53,430kB)
   - Windows.Xbox.Management.idl (68,873kB)
   - Windows.Xbox.Media.idl (516kB)
   - Windows.Xbox.Shell.idl (33,135kB)
   - Windows.Xbox.Shell.Social.idl (3,030kB)
   - Windows.Xbox.System.idl (833kB)
   - Windows.Xbox.Achievements.idl (29,850kB)


4. Build the project   
   - Note: You may need to build the Detours separately.
   - You can build any part of the project by selecting individual solution(s), right-clicking, and clicking "Build Selection"
   
## Other
### Generating IDLs from WinMDs
TODO

# Contributing
TODO