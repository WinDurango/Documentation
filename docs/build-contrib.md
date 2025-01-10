# Setup

## Prerequisites

1. Windows 10 (or later)
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

## Building

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

## Using
Note that BuildType in this case is the dropdown that is shown at the top of the IDE (usually Debug) near the Local Windows Debugger button, you have a few choices, namely Release.
1. Copy the DLLs from `x64\{BuildType}` as well as the DLL from the inner `winrt_x` folder into the same folder as the Xbox program's executable. 
   
## Other
### Generating IDLs from WinMDs
TODO

# Contributing
TODO