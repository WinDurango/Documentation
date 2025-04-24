# Setup

## Part 1: Prerequisites

### To launch
1. Your computer must be 64 bit and running Windows 10 or 11

2. Enable Developer Mode 
	- For Windows 10: Settings > Windows Update > For Developers 
	- For Windows 11: Settings > System > For Developers
3. Download the `Windows App SDK` at https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads

4. Download the [2012 Visual C++ Redistributables](https://www.microsoft.com/en-us/download/details.aspx?id=30679) and the [Latest Visual C++ Redistributables](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version)

5. Download Graphics Tools
	- For Windows 10: Settings > Apps > Optional Features
	- For Windows 11: Settings > System > Optional Features

6. Download `Visual Studio 2022 Community` at https://visualstudio.microsoft.com/downloads/ and then in the Visual Studio Installer, goto the `Workloads` tab and select `Desktop development with C++`
	
7. Download the latest release https://github.com/WinDurango/WinDurango/releases or artifact https://github.com/WinDurango/WinDurango/actions of Windurango. (Note: You need to be signed into a github account in order to download the latest artifact from Github actions). If you want better performance you may also download the other `d3d11_x.dll` and use it instead of the default one. 

8. Have a decrypted copy of your Xbox One game. This can be legally obtained from an exploited Xbox One with Durango Dumpling.

### To build
1. Everything from [the launch requirements](#to-launch) (except for the release/artifact)
   
3. Windows 10 (or later)
   
5. Windows App SDK
   
7. Visual Studio 2022
   
9. Git
    
11. Windows 11 SDK version 10.0.17134.0 or later
    
13. The following from the Visual Studio Installer

    - In the workloads tab, select

        - .NET desktop development
		  - Desktop development with C++
		  - Game development with C++

    - In the workloads tab, select


		- MSVC v143 - VS 2022 C++ x64/x86 build tools (Latest)
		- C++ Universal Windows Platform support for v143 build tools (ARM64/ARM64EC)
		- Windows 11 SDK (latest version)
    
    
11. The project cloned to a folder
   
## Part 2: Registering and Running the UWP Package

1. Locate the "Mount" Folder in your Xbox Game files (For Minecraft you should see Minecraft.Client.exe in it.) Copy the mount folder to an easily accessible location (ie: your documents folder or the root of your hard drive). Don't worry about the EmbeddedXvd folder or era.vbi file as they are not needed. 

2. Extract all of the `.dll` files from Windurango and place them into the Mount folder. If you want to use the other `d3d11_x.dll`, copy it to the mount folder and replace the default one with it. 

3. Open windows Powershell and navigate to your mount folder. The easiest way to do this is to copy the file path in File Exploerer by clicking on the top file path bar and pressing ctl+c once it is highlighted. Then in Powershell, type in the command `cd File Path` where `File Path` is where you paste the file path you just copied. Use quotation marks if there is a space in the file path (ie `C:\Users\User Name\Xbox Game` should be `"C:\Users\User Name\Xbox Game"`. Alternatively you can simply use a file path without spaces, such as `C:\Xbox_Game`)

4. Once in the mount folder, run `Add-AppxPackage -Path AppxManifest.xml -Register` (or `Add-AppXPackage -Register .\AppxManifest.xml`). This will add the game to your start menu. (Note: This step requires [Developer mode](#to-launch) to be enabled otherwise you will get an error)

5. From here, you should be able to launch the game from your start menu. A cmd window should also appear and various logs should show up. Dont worry if a million errors show up, that is normal since this is still very early in development. If the game closes almost instantly with no error messages, then you are likely missing dependencies from Visual Studio.

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

### Installing Mods
Mods are in the .dll file format.
In your mount folder, create a new folder called mods and copy whatever mod .dll files you have to it. Note that many mods are extremely version specific (ex. a minecraft mod for version 1.61.0.1 will crash on version 1.61.0.2) so make sure you have the correct version of either the game or the mod (Note to mod devs: PLEASE specify the version of the game you used to make the mod to aleviate this issue). 

# Contributing
TODO
