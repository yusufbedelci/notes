[C#](csharp)
[C# OODP](csharp_oodp)
[C# Generics](csharp_generics)
[C# Interfaces](csharp_interfaces)

---
# C# `IComparable`
In C#, the `IComparable` or `IComparable<T>` interfaces require you to define a `.CompareTo()` method. This method is used by `Sort` methods to compare objects with each other and sort them.

The `.CompareTo()` method returns an integer value and this can be interpreted in the following way:
- `< 0` (less than zero) -> Current object is less than the object being compared to.
- `0` (equal to zero) -> Current object is equal to the object being compared to.
- `> 0` (greater than zero) -> Current object is greater than the object being compared to.

Usually value types like `int` or `string` already have `.CompareTo()` implemented. You can use these if you need to check them in the `.CompareTo()` method of a more complex class.

(`IComparable<T>` is type safe, and you can assume the correct type is entered as argument. With `IComparable` any type can be entered as an argument, and therefore you would need to cast the type before applying comparisons).

## Implementation
```csharp
public class Person : IComparable<Person>
{
	public string Name { get; set; }
	public int Age { get; set; }

	public Person(string name, int age)
	{
		Name = name;
		Age = age;
	}

	public int CompareTo(Person other)
	{
		// first compare by name
		int nameComparison = Name.CompareTo(other.Name);
		if (nameComparison != 0)
			return nameComparison;

		// if names are equal, compare by age
		return Age.CompareTo(other.Age);
	}
}
```