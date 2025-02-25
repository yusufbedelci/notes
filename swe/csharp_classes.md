[C#](csharp)
[C# OODP](csharp_oodp)

---
# C# Classes
Classes are a fundamental construct in C# for creating objects. They act as blueprints for objects, defining the properties (fields), behaviors (methods), and states (constructors) of the objects.

## Fields & Constructors
Fields are values that are stored in the object, and that are pertinent to the class/object. A constructor is a method that initializes a new instance of a class. They have the same name as the class and may have parameters. If you don't define a constructor, C# generates a parameterless constructor that initializes all members variables to their default values. You can define your own constructor to set up initial state or perform actions when an object is created.

```csharp
public class Person
{
	public string Name; // Field
	public int Age; // Field

	// Constructor
	public Person(string name, int age)
	{
		Name = name;
		Age = age;
	}
}
```

### Fields with `const` and `readonly`
- `const` -> compile-time constant, value is set at compile time and cannot be changed.
- `readonly` -> run-time constant, value can be set at run time, but only in the constructor.
```csharp
public class Constants
{
	public const double Pi = 3.14159;
	public readonly string Name;

	public Constants(string name)
	{
		Name = name;
	}
}
```

## Class methods
Class methods are methods of a class that define it's behavior. They can use and modify the fields of the class.
```csharp
public class Person
{
	public string Name;
	private int age;

	public void DisplayInfo()
	{
		Console.WriteLine($"Name: {Name}, Age: {age}");
	}
}
```

## Class with Lists and/or Objects as Fields
Classes can have complex types like lists or other objects as fields, allowing intricate data structures.
```csharp
public class Company
{
	public string Name;
	public List<Person> Employees;

	public Company()
	{
		Employees = new List<Person>();
	}
}
```

## Dealing with `null`
The `?` operator can be used with data types to indicate that the variable can hold a `null` value. This can be useful in constructors or methods to check for null and avoid `NullReferenceException`.
```csharp
public class Person
{
	public string? Name; // Can be null

	public Person(string? name)
	{
		Name = name ?? "Unknown"; // Null-coalescing operator
	}
}
```

## Static fields, methods, and classes
With the `static` keyword we can adjust the structure and usage of classes and their members. Static members belong to the class itself rather than any instance. Static methods can be called on the class itself not on an instance. A static class cannot be instantiated, only contains static members.
```csharp
public static class Calculator
{
	public static int lastResult = 0;
	
	public static int Add(int a, int b)
	{
		lastResult = a + b;
		return lastResult;
	}
}
```