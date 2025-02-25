[C#](csharp)
[C# OODP](csharp_oodp)

---
# C# Methods
Methods are blocks of code that perform specific tasks and can be called from other parts of your program. In C#, methods are defined within classes or structs, and they have return type, a name, and optionally a list of parameters.

## Basic structure of a method
- **Return type** -> indicates the type of value the method returns. If the method does not return a value, the return type is `void`.
- **Method name** -> the name of a method, following the conventions.
- **Parameters** -> optional list of parameters the method accepts, parameters are enclosed in parentheses and are comma-separated.

## Examples
With a return type:
```csharp
public int Add(int number1, int number2)
{
	int result = number1 + number2;
	return result;
}
```

Without a return type:
```csharp
public void DisplayMessage(string message)
{
	Console.WriteLine(message);
}
```

## Expression-embodied methods
Expression-bodied methods provide a concise syntax to define a method with a single expression. This feature is especially useful for simple methods.
```csharp
pubic int Add(int num1, int num2) => num1 + num2;
```

## Tips and best practices
Use meaningful names that clearly indicate what the method does. Keep methods short and focused on a single task, this makes your code more readable and maintainable. Prefer passing parameters for input and output over using global variables. You can have multiple methods with the same name but different parameters, this is called overloading and allows you to handle different scenarios with the same method name.