
# ... / ILSpy / README

## ILSpy

### [ ilspy - Google 搜尋 ](https://www.google.com/search?q=ilspy&oq=ilspy) 

### [ 取得 ILSpy - Microsoft Store zh-TW ( Microsoft Store ) ](https://www.microsoft.com/zh-tw/p/ilspy/9mxfbkfvsq13?activetab=pivot:overviewtab)

## @ GitHub

ILSpy is the open-source .NET assembly browser and decompiler.
Download: latest release | latest CI build (master) | Microsoft Store (RC & RTM versions only)

Decompiler Frontends
Aside from the WPF UI ILSpy (downloadable via Releases, see also plugins), the following other frontends are available:

Visual Studio 2019 ships with decompilation support for F12. To enable, go to Tools / Options / Text Editor / C# / Advanced and check "Enable navigation to decompiled source"
C# for Visual Studio Code ships with decompilation support as well. To enable, activate the setting "Enable Decompilation Support".
Visual Studio 2017/2019 extension marketplace
Visual Studio Code Extension repository | marketplace
ICSharpCode.Decompiler NuGet for your own projects
Linux/Mac/Windows ILSpy UI based on Avalonia - check out https://github.com/icsharpcode/AvaloniaILSpy
dotnet tool for Linux/Mac/Windows - check out ICSharpCode.Decompiler.Console in this repository
Linux/Mac/Windows PowerShell cmdlets in this repository
Features
Decompilation to C#
Whole-project decompilation (csproj, not sln!)
Search for types/methods/properties (substring)
Hyperlink-based type/method/property navigation
Base/Derived types navigation, history
BAML to XAML decompiler
Extensible via plugins (MEF)
Check out the language support status
License
ILSpy is distributed under the MIT License. Please see the About doc for details, as well as third party notices for included open-source libraries.

How to build
Windows:

Install Visual Studio (documented version: 16.4) with the following components:
Workload ".NET Desktop Development". This includes by default .NET Framework 4.8 SDK and the .NET Framework 4.7.2 targeting pack, as well as the .NET Core 3.1 SDK (ILSpy.csproj targets .NET 4.7.2, and ILSpy.sln uses SDK-style projects).
Workload "Visual Studio extension development" (ILSpy.sln contains a VS extension project)
Individual Component "MSVC v142 - VS 2019 C++ x64/x86 build tools (v14.23)" (or similar)
The VC++ toolset is optional; if present it is used for editbin.exe to modify the stack size used by ILSpy.exe from 1MB to 16MB, because the decompiler makes heavy use of recursion, where small stack sizes lead to problems in very complex methods.
Check out the ILSpy repository using git.
Execute git submodule update --init --recursive to download the ILSpy-Tests submodule (used by some test cases).
Open ILSpy.sln in Visual Studio.
NuGet package restore will automatically download further dependencies
Run project "ILSpy" for the ILSpy UI
Use the Visual Studio "Test Explorer" to see/run the tests
Note: Visual Studio 16.3 and later include a version of the .NET Core SDK that is managed by the Visual Studio installer - once you update, it may get upgraded too. Please note that ILSpy is only compatible with the .NET Core 3.1 SDK and Visual Studio will refuse to load some projects in the solution (and unit tests will fail). If this problem occurs, please manually install the .NET Core 3.1 SDK from here.

Unix / Mac:

Make sure .NET Core 2.1 LTS Runtime is installed (you can get it here: https://get.dot.net).
Make sure .NET Core 3.1 SDK is installed.
Make sure PowerShell is installed (formerly known as PowerShell Core)
Check out the repository using git.
Execute git submodule update --init --recursive to download the ILSpy-Tests submodule (used by some test cases).
Use dotnet build Frontends.sln to build the non-Windows flavors of ILSpy (.NET Core Global Tool and PowerShell Core).
How to contribute
Report bugs
If you want to contribute a pull request, please add https://gist.github.com/siegfriedpammer/75700ea61609eb22714d21885e4eb084 to your .git/hooks to prevent checking in code with wrong indentation. We use tabs and not spaces. The build server runs the same script, so any pull requests using wrong indentation will fail.
Current and past contributors.

Privacy Policy for ILSpy
ILSpy does not collect any personally identifiable information, nor does it send user files to 3rd party services. ILSpy does not use any APM (Application Performance Management) service to collect telemetry or metrics.

### [ icsharpcode/ILSpy: .NET Decompiler with support for PDB generation, ReadyToRun, Metadata (&more) - cross-platform! ](https://github.com/icsharpcode/ILSpy)

### [ Release ILSpy 6.2.1 · icsharpcode/ILSpy ](https://github.com/icsharpcode/ILSpy/releases/tag/v6.2.1)

