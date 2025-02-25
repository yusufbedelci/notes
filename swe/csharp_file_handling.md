[C#](csharp)

---
# C# File Handling
## Reading from & Writing to Files in C# 
C# provides different ways to work with files, mainly using the `System.IO` namespace.
### Reading from a file
We can read a file in different ways:
- `File.ReadAllText()` -> reads the entire file as a string.
- `File.ReadAllLines()` -> reads the file *line by line* into an array.
- `File.ReadAllBytes()` -> reads binary files (e.g. images, videos).

```csharp
string file = "data.txt";
try
{
	string content = File.ReadAllText(file);
	Console.WriteLine("File content:\n" + content);
}
catch (Exception ex)
{
	Console.WriteLine($"Error reading from file: {ex.Message}");
}
```

### Writing to a file
We can write to a file in different ways:
- `File.WriteAllText()` -> creates a file if it doesn't exist, overwrites it if it does.
- `File.AppendAllText()` -> adds new content without overwriting the file.
- `File.WriteAllLines()` -> writes an array of string to a file.

```csharp
string file = "data.txt";
string content = "Hello!";
try
{
	File.WriteAllText(file, content);
	Console.WriteLine("File written successfully.");
}
catch (Exception ex)
{
	Console.WriteLine($"Error writing to file: {ex.Message}");
}
```

### Exception handling
When working with files many things can go wrong:
- `FileNotFoundException` -> the file doesn't exist.
- `UnauthorizedAccessException` -> there may be permission issues.
- `IOException` -> the file could be locked

```csharp
string file = "data.txt";

try
{
	string content = File.ReadAllText(file);
	Console.WriteLine("File content:\n " + content);
}
catch (FileNotFoundException) => Console.WriteLine("File not found!");
catch (UnauthorizedAccessException) => Console.WriteLine("Access denied!");
catch (Exception ex) => Console.WriteLine(ex.Message);
finally => Console.WriteLine("Operation completed!");
```