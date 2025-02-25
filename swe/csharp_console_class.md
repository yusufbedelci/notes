[C#](csharp)
[C# Basics](csharp_basics)

---
# C# `Console` class
The `Console` class in the `System` namespace is a standard class that provides basic support for reading from and writing to the console. Here are some of the most commonly used methods of the `Console` class.

## `Console.WriteLine()`
Writes the specified data, followed by the current line terminator, to the standard output stream.
```csharp
Console.WriteLine("Hello, World!");
```
Tip: It automatically appends a new line at the end of the output.

## `Console.Write()`
Write the specified data to the standard output stream without a newline character at the end.
```csharp
Console.Write("Enter your name:");
```
Tip: Useful when you want to continue on the same line, such as prompting a user for input.

## `Console.ReadLine()`
Reads the next line of characters from the standard input stream. It returns a `string` by default and has to be manually converted to another type.
```csharp
string ageInput = Console.ReadLine();
bool inputIsCorrect = int.TryParse(ageInput, out int age);
if (inputIsCorrect)
{
	// if input was correct do something with age.
}
else
{
	// Handle the error, maybe prompt the user again.
}
```
Tip: Direct conversion (e.g., `int.Parse(Console.ReadLine())`) can throw exceptions if the input is not in the expected format. It's safer to use `TryParse()` methods, which handle incorrect formats more gracefully.

