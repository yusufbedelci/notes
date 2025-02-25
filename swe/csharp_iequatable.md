[C#](csharp)
[C# OODP](csharp_oodp)
[C# Generics](csharp_generics)
[C# Interfaces](csharp_interfaces)

---
# C# `IEquatable`
In C#, the `IEquatable` interface requires you to overload the `.Equals()` method with a parameter of a specific type. This method can be used to check whether the object of the given class/type is equal to another object of the same class/type.

**Tip**: Ensure to always override the default implementation of `.Equals()` and `.GetHashCode()` methods of the `Object` class.
## Implementation
```csharp
public class Person : IEquatable<Person>
{
	public string Name { get; set; }
	public int Age { get; set; }

	public Person(string name, int age)
	{
		Name = name;
		Age = age;
	}

	// overriding the virtual Equals method defined in Object class
	public override bool Equals(object obj) => Equals(obj as Person);

	// implementation of IEquatable<T>
	public bool Equals(Person other)
	{
		if (other is null)
			return false;

		return Name == other.Name && Age == other.Age;
	}

	// overriding the GetHashCode method defined in Object class
	public override int GetHashCode() => HashCode.Combine(Name, Age);
}
```