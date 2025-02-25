[C#](csharp)
[C# Basics](csharp_basics)

---
# Namespaces
Namespaces are a fundamental part of C# and .NET used to organize and provide a level of separation for your classes, structures, and other types.
## Traditional namespace declaration
Traditionally, namespaces in C# are declared using the `namespace` keyword, and the namespace scope is defined by curly braces `{}`. All the types (classes, structs, enums, etc.) defined within those braces are part of the namespace.

```csharp
namespace MyProject.Models
{
    class User
    {
        // Implementation
    }

    class Product
    {
        // Implementation
    }
}
```

In this structure, both `User` and `Product` classes are part of the `MyProject.Models` namespace. To use these classes in other parts of your application (in different namespaces), you would typically use the `using` directive at the top of your C# file:

```csharp
using MyProject.Models;

class Program
{
	User user = new User();
	Product product = new Product();
}
```

## File-scoped namespaces
Starting with C# 10, you can declare namespaces without the need for braces, making the entire file part of the declared namespace. This is known as a file-scoped namespace. The syntax is cleaner and reduces the level of indentation required, making the code more readable.
```csharp
namespace MyProject.Models;

class User
{
	// Implementation
}

class Product
{
	// Implementation
}
```
With file-scoped namespaces, the entire file is implicitly scoped to the declared namespace (`MyProject.Models` in this case), and there's no need for the curly braces. This feature is particularly beneficial in projects with deep folder structures and many files, each containing a single type.

## Advantages of File-scoped namespaces
File-scoped namespaces reduce nesting and indentation, making the code easier to read and maintain. It makes it clear that the types in a file belong to the specified namespace without the visual clutter of additional braces. It also encourages keeping one type per file, which is a common best practice in C# projects, enhancing the organization and structure of the codebase.