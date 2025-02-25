[C#](csharp)
[C# OODP](csharp_oodp)
[C# Polymorphism](csharp_polymorphism)

---
# C# Generics
Generics in C# are a powerful feature that allows you to write flexible, reusable, and type-safe code. They enable you to define classes, interfaces, methods, and properties with placeholders for one or more types.

- **Type Safety**: Generics provide compile-time type checking. Operations on generic types are checked at compile time, reducing runtime errors.
- **Reusability**: You can use generic classes and methods with different data types without rewriting or duplicating code.
- **Performance**: Using generics can boost performance by eliminating the need for boxing and unboxing when dealing with value types.

## Generic fields
A generic field is a variable within a class or struct that can hold any data type, specified when an instance of the generic class is created. However, C# does not allow non-generic classes to have generic fields. Generic fields are typically declared within generic classes or structs. Properties can also be made generic in C#.

In the following example, `T` is a placeholder for any data type, and the `Value` field can store data of any type specified when an instance of `GenericContainer<T>` is created:
```csharp
public class GenericContainer<T>
{
	public T Value; // Generic field
}

var intContainer = new GenericContainer<int>();
intContainer.Value = 123;

var stringContainer = new GenericContainer<string>();
stringContainer.Value = "Hello, Generics!";
```

## Generic methods
Generic methods are methods within a non-generic or generic class that perform operations on a specified type `T`. The type `T` can be different from the type parameters used in the class.

The following `Sort` method is a generic method in the non-generic class `Sorter`:
```csharp
public class Sorter
{
	public void Sort<T>(T[] items) where T: IComparable<T>
	{
		// Implementation of sorting algorithm
	}
}
```

## Multiple generic types
You can apply multiple generic types to a class or method:

A class with generic types:
```csharp
public class KeyValuePair<TKey, TValue>
{
	public TKey Key { get; set; }
	public TValue Value { get; set; }

	public KeyValuePair(TKey key, TValue value)
	{
		Key = key;
		Value = value;
	}

	public void Display() => Console.WriteLine($"Key: {Key}, Value: {Value}");
}
```

A method with generic types:
```csharp
public void PrintPair<T1, T2>(T1 first, T2 second)
{
	Console.WriteLine($"First: {first}, Second: {second}");
}
```

## Default values
The default value of reference types is `null`. The default value of value types could differ depending on the type, for example for numeric types this would be `0`, for `bool` it is `false`. You can use the `default` keyword/method to set the default value of a generic type:
```csharp
int num = default;
T? something = default(T); // or just simply -> default;
```