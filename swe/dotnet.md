[C#](csharp)

---
# .NET

## Solutions and projects in .NET
### What is a Solution (.sln)?
- A **solution** is a container that organizes multiple **projects** within a .NET application.
- It keeps track of dependencies, references and project relationships.
- File -> `.sln` (Solution file).
### What is a Project (.csproj)?
- A **project** represents a single .NET application/library within a solution.
- It contains source code, dependencies, and settings.
- File -> `.csproj` (Project file), defines project configurations.
### Common project types
| Project Type                          | Descriptions              |
| ------------------------------------- | ------------------------- |
| Console App (`dotnet new console`)    | CLI-based application.    |
| Class Library (`dotnet new classlib`) | Reusable code (DLL).      |
| ASP.NET Web API (`dotnet new webapi`) | RESTful API.              |
| ASP.NET MVC (`dotnet new mvc`)        | Web app with MVC pattern. |
| xUnit Tests (`dotnet new xunit`)      | Unit test project.        

## Package management in .NET
### NuGet - The Official Package Manager
- .NET uses NuGet to manage third-arty libraries & dependencies.
- NuGet packages are hosted on https://nuget.org.
- Dependencies are stored in the `csproj` file and `packages.lock.json`.

- Installing a package -> `dotnet add package Newtonsoft.Json`
- Restore dependencies -> `dotnet restore`
- Remove a package -> `dotnet remove package Newtonsoft.Json`

### Package Manager Console (PMC) in Visual Studio
The Package Manager Console (PMC) in Visual Studio is a built-in PowerShell terminal used to manage NuGet Packages for your .NET projects. It allows you to install, update, and uninstall packages using NuGet commands directly from the IDE. The PMC is only available in Visual Studio and is **not** included in VS Code.