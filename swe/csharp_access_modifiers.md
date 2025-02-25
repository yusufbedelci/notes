[C#](csharp)
[C# OODP](csharp_oodp)
[C# Encapsulation](csharp_encapsulation)

---
# C# Access modifiers
Access modifiers allow you to define the scope and visibility of *class members* (fields, properties, methods).

C# provides several access modifiers to control access levels:
- `public`: member is accessible from any other class
- `private`: member is accessible only within its own class
- `protected`: member is accessible within its own class and derived class instances

## Private members
The purpose of the `private` access modifier is to hide the class' internal state and protect it from unintended modification from outside.
- Private fields: store data that should only be accessed or modified through class methods.
- Private methods: implement functionality that is internal to the class and not intended to be part of the class' interface with the outside world.

```csharp
public class BankAccount
{
	private double _balance; // private field, (starts with underscore and uses lower camel-case by convention).

	public BankAccount(double initialBalance) => _balance = initialBalance;

	private void CalculateInterest() // private method
	{
		// implementation...
	}

	public void AddInterest()
	{
		CalculateInterest();
		// other operations...
	}
}
```

## Protected members
The purpose of the `protected` access modifier is to allow a class to expose some of its members to derived classes while keeping them hidden from other classes.
- Protected fields: useful when you want derived classes to have direct access to the field.
- Protected methods: allow derived classes to utilize or override a method's behavior.

```csharp
public class Person
{
	protected string Name; // protected field

	protected void DisplayName() // protected method
	{
		Console.WriteLine(Name);
	}
}

public class Employee : Person
{
	public Employee(string name) => Name = name;

	public void Introduce() => DisplayName(); // Accessing protected method
}
```

## Key concepts
- Encapsulation via access modifiers is crucial for hiding the internal state of an object and protecting it from outside interference and misuse.
- `private` members are only accessible within the class they are declared in, providing a mechanism to enforce encapsulation.
- `protected` members extend accessibility to derived classes, allowing for more flexible class hierarchies and reuse of base class logic.
- Using these access modifiers correctly is essential for good class design, ensuring that a class' interface within the rest of the application is clear, intentional, and safe.