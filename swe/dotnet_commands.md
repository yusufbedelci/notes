[.NET](dotnet)

---
# .NET (CLI) Commands
The .NET CLI (`dotnet`) is essential for managing projects.

## Project & Solution management
| Command                              | Description                       |
| ------------------------------------ | --------------------------------- |
| `dotnet new console -n MyApp`        | Create a new console app.         |
| `dotnet new webapi -n MyApi`         | Create a new Web API project.     |
| `dotnet new sln -n MySolution`       | Create a new solution file.       |
| `dotnet sln add MyProject.csproj`    | Add a project to a solution.      |
| `dotnet sln remove MyProject.csproj` | Remove a project from a solution. |

## Building & Running
| Command        | Description                |
| -------------- | -------------------------- |
| `dotnet build` | Compile the project.       |
| `dotnet run`   | Run the project.           |
| `dotnet clean` | Remove the compiled files. |

## Testing
| Command             | Description                             |
| ------------------- | --------------------------------------- |
| `dotnet test`       | Run unit tests.                         |
| `dotnet watch test` | Run tests continuously on file changes. |

## Dependency Management
| Command                        | Description              |
| ------------------------------ | ------------------------ |
| `dotnet add package <name>`    | Install a NuGet package. |
| `dotnet remove package <name>` | Remove a NuGet package.  |
| `dotnet list package`          | List installed packages. |

## Publishing & Deployment
| Command                            | Description                       |
| ---------------------------------- | --------------------------------- |
| `dotnet publish -c Release -o out` | Publish a project for deployment. |
| `dotnet restore`                   | Restore dependencies.             |
