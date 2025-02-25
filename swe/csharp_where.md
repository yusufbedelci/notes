[C#](csharp)
[C# OODP](csharp_oodp)
[C# Generics](csharp_generics)
[C# Interfaces](csharp_interfaces)

---
# C# `where` keyword
In C#, the `where` keyword is used in conjunction with generics to specify constraints on the type parameters. It allows you to restrict the types that can be used as arguments for the generic type parameters. When using the `where` keyword you can define constraints based on various criteria, such as base classes, interfaces, or the presence of a parameterless constructor. This helps you ensure that the generic types satisfy certain requirements and have specific capabilities. You can use a `where` constraint on generic types, on a class level as well as a method level.

## Base class constraint
```csharp
public class MyClass<T> where T: MyBaseClass
{
	// implementation
}
```

## Interface constraint
```csharp
public class MyClass<T> where T: class, IAnimal
{
	// implementation
}
```
OR
```csharp
public T SearchAnimal<T>(string name) where T : class, IAnimal
{
	// Implementation
}
```