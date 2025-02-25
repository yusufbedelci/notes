[C#](csharp)
[C# OODP](csharp_oodp)
[C# Encapsulation](csharp_encapsulation)

---
# C# Properties
Properties in C# are members that provide a flexible mechanism to read, write, or compute the values of private fields. Properties can encapsulate data with a combination of `get` and `set` accessors, making them more than just simple field accessors.

## `get` and `set` accessors
- `get` accessor is used to return the property value.
- `set` accessor is used to assign a new value. The `value` keyword represent the value being assigned by the accessor.
```csharp
public class Person
{
	private string _name;

	public string Name
	{
		get { return _name; }
		set { _name = value; }
	}
}
```

## Auto-implemented properties
When no additional logic is required in the property accessors, you can use auto-implemented properties, which automatically create a private and anonymous ***backing field***.
```csharp
public class Person
{
	public string Name { get; set; }
}
```

## Read-only properties
Read-only properties include a `get` accessor but not `set` accessor. They can be initialized either at declaration or within a constructor.
```csharp
public class Person
{
	public string Name { get; } // = "Anon"; // with a default value at declaration

	public Person(string name) => Name = name;
}
```

## Property set validation
Validation can be added in the `set` accessor to enforce rules for what values are acceptable.
```csharp
private int _age;
public int Age
{
	get { return _age; }
	set
	{
		if (value >= 0) _age = value;
		else throw new ArgumentException("Age cannot be negative.");
	}
}
```

## Virtual and override properties
Properties can be virtual and overridden in derived classes, similar to methods.
```csharp
public class BaseClass
{
	public virtual string Name { get; set; }
}

public class DerivedClass : BaseClass
{
	private string name;
	public overridde string Name
	{
		get { return name; }
		set { name = value + " Jr."; }	
	}
}
```

## Access modifiers for properties
You can specify different access levels for the `get` and `set` accessors to control their visibility.
```csharp
public class Person
{
	public string Name { get; private set; } // Name can be set only within the class
}
```

## Key concepts
- **Encapsulation**: Properties are a cornerstone of encapsulation in object-oriented programming, allowing for controlled access and modification of data.
- **Data validation**: The `set` accessor provides a convenient place to perform validation, ensuring data integrity.
- **Flexibility**: Properties support a range of configurations, including read-only, write-only, and full read/write, as well as different accessibility levels for `get` and `set`.
- **Inheritance**: Virtual properties enable derived classes to customize or extend base class property behavior.