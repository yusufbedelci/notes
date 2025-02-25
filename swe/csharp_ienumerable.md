[C#](csharp)
[C# OODP](csharp_oodp)
[C# Generics](csharp_generics)
[C# Interfaces](csharp_interfaces)

---
# C# `IEnumerable`
In C#, the `IEnumerable` interface and `yield return` statement are powerful features that facilitate iteration over a collection of objects. By implementing `IEnumerable` you can create custom collections that can be used with `foreach` loops and other iteration contexts. The `yield return` statement is used within an iterator block to provide a value to the enumerator object or to signal the end of iteration.

**Tip**: Implementing `IEnumerable` in your classes makes them compatible with the foreach loop and LINQ queries, enhancing their usability and flexibility in C#.

## Implementing the `IEnumerable` interface
When you implement `IEnumerable` in a class, you're essentially making it possible to enumerate over its elements. `IEnumerable` requires that you implement the `GetEnumerator` method, which returns an `IEnumerator`. The `IEnumerator` interface has methods to move to the next element, and properties to get the current element in the collection.

```csharp
public class Person
{
	public string Name { get; set; }

	public Person(string name) => Name = name;
}

public class People : IEnumerable<Person>
{
	private Person[] _people;

	public People(Person[] peopleArray)
	{
		_people = new Person[peopleArray.Length];
		for (int i = 0; i < peopleArray.Length; i++)
			_people[i] = peopleArray[i];
	}

	public IEnumerator<Person> GetEnumerator()
	{
		for (int i = 0; i < _people.Length; i++)
			yield return _people[i]; // `yield return` simplifies the enumerator implementation
	}

	IEnumerator IEnumerable.GetEnumerator()
	{
		return GetEnumerator();
	}
}
```