[C#](csharp)
[C# File Handling](csharp_file_handling)

---
# C# JSON
To work with JSON, we can use the `Newtonsoft.Json` library (`Json.NET`). We can do this by installing it via NuGet:
```mathematica
Instal-Package Newtonsoft.Json
```

## Serializing an object to JSON
Convert a C# object into a JSON string and save it to file:
```csharp
using System;
using System.IO;
using Newtonsoft.Json;

class Student
{
	public string Name { get; set; }
	public int Age { get; set; }
}

class Program
{
	static void Main()
	{
		Student student = new Student { Name = "Alice", Age = 22 };
		string json = JsonConvert.SerializeObject(student, Formatting.Indented);
		File.WriteAllText("student.json", json);
	}
}
```

## Deserializing JSON
Convert a JSON string back into a C# object:
```csharp
string json = File.ReadAllText("student.json");
Student student = JsonConvert.DeserializeObject<Student>(json);

Console.WriteLine($"Name: {student.Name}, Age: {student.Age}");
```