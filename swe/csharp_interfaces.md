[C#](csharp)
[C# OODP](csharp_oodp)
[C# Abstraction](csharp_abstraction)

---
# C# Interfaces
In C#, interfaces define a contract that classes or structs can implement. They specify a set of methods, properties, events or indexers without providing an implementation. Interfaces are used to achieve abstraction, polymorphism and multiple inheritance in C#.

## Creating interfaces
An interface is declared using the `interface` keyword. It can contain declarations of methods, properties, events, and indexers.
```csharp
public interface IIdentifiable
{
	string Id { get; }
}
```

## Implementing interface members
A class or struct that implements an interface must provide an implementation for all its members.
```csharp
public class Product : IIdentifiable
{
	public string Id { get; private set; }

	public Product(string id) => Id = id;
}
```

## Implementing multiple interfaces
A class can implement multiple interfaces, separating each interface with a comma.
```csharp
public interface IStorable
{
	void Save();
}

public interface IRetrievable
{
	void Load();
}

public class Document : IStorable, IRetrievable
{
	public void Save() { /* implementation... */ }
	public void Load() { /* implementation... */ }
}
```

## Creating interfaces with multiple members
Interfaces can define more than one method, property, etc.
```csharp
public interface ICRUD
{
	void Create();
	void Read();
	void Update();
	void Delete();
}
```

## Creating interfaces with properties
Interfaces can include property definitions.
```csharp
public interface IPerson
{
	string Name { get; set; }
	int Age { get; }
}
```

## Working with interface objects
You can use an interface as a variable type. This allows for polymorphic behavior.
```csharp
ICRUD myObject = new SomeCRUDImplementation();
myObject.Create();
```

## Interface inheritance
Interfaces can inherit from other interfaces, allowing for a hierarchical organization of abstraction.
```csharp
public interface IAdvancedCRUD : ICRUD
{
	void SoftDelete();
}
```

## Writing classes with interfaces as members
You can use interfaces as types for fields, properties, method parameters, or return types within classes.
```csharp
public class Repository
{
	private ICRUD crudService;

	public Repository(ICRUD service) => crudService = service;
}
```
### Deriving and implementing in the same class
A class can derive from a base class and implement one or more interfaces simultaneously.
```csharp
public class AdvancedDocument : Document, IAdvancedCRUD
{
	public void SoftDelete() { /* implementation... */ }
	// implementations of ICRUD methods come from the Document base class
}
```

## Key Concepts
- **Abstraction**: Interfaces provide a high level of abstraction, allowing you to define what a class does without specifying how it does it.
- **Polymorphism**: Interfaces enable polymorphism. A single interface reference can point to different implementations, allowing for flexible and interchangeable objects.
- **Decoupling**: By programming to an interface rather than a specific implementation, you can decouple components of your application, making them easier to extend and maintain.