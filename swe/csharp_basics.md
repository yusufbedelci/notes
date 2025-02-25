[C#](csharp)

---
# C# Basics

## The `Main` method
The `Main` method is the entry point of a C# application. When the application starts it looks for the `Main` method to begin execution. The `Main` method is typically inside of a `class` that is inside of a namespace.
```csharp
class Program
{
	static void Main(string[] args)
	{
		// The code goes in here.
	}
}
```
Tip: the `args` parameter represents the command line arguments passed to the program. It's an array of strings.
## Specifying types
In C# you can use explicit or implicit typing when defining a variable.
### Explicit typing
This is used when you want to be clear about the type or when the type can't be inferred:
```csharp
int number;
number = 5;

int age = default; // will get the default value for the given type.
```
### Implicit typing
This is when you use the `var` keyword to define a variable, and the compiler will infer the type by the assigned value. The actual type is determined at compile-time, so `var` still maintains strong typing.
```csharp
var name = "Keefle"; // type of string.
```
Tip: use `var` to make the code cleaner especially when the type is obvious or verbose. Sometimes `var` can make code less readable, especially when the type of the assigned value isn't obvious, so use it judiciously to maintain code clarity.