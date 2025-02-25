[C#](csharp)
[C# OODP](csharp_oodp)
[C# Abstraction](csharp_abstraction)

---
# C# Abstract Classes
In C#, abstract classes serve as a foundational class that cannot be instantiated on their own but can be subclassed. They are used to define a common set of behaviors and properties that can be inherited by derived classes, ensuring a certain level of uniformity while also allowing for class-specific implementations of certain behaviors.

## Creating abstract classes
An abstract class is defined using the `abstract` keyword. It can contain both abstract and concrete members. Abstract members are methods (or properties) without any implementation, requiring derived classes to provide an implementation.
```csharp
public abstract class Vehicle
{
	public abstract void Drive();

	public void Start() => Console.WriteLine("Vehicle starting...");
}
```
In this example, `Vehicle` is an abstract class with an abstract method `Drive` and a concrete method `Start`.

## Creating classes derived from abstract classes
Derived classes extend abstract classes by providing implementations for abstract members. A derived class must implement all abstract methods and properties of its abstract base class unless the derived class is also declared as abstract.
```csharp
public class Car : Vehicle
{
	public override void Drive() => Console.WriteLine("Car is driving...");
}
```
In this example, `Car` is a concrete class that derives from the abstract class `Vehicle`, and provides an implementation for the `Drive` method.

## Casting derived classes to their abstract base classes
Casting an instance of a derived class to its abstract base class is a way to interact with it through a more generalized interface. This is useful for working with collections of objects that share a common base but have different implementations.
```csharp
Vehicle myCar = new Car();
myCar.Drive(); // Calls the Drive implementation in Car
myCar.Start(); // Calls the Start method defined in Vehicle
```
In this example `myCar` is declared as a `Vehicle` but instantiated as a `Car`. This demonstrated polymorphism; the `Drive` method called is the one implemented in `Car`, while `Start`, not overridden, calls the base class implementation.

## Key concepts
- **Abstraction**: Abstract classes provide a way to define a template for other classes. They can specify a part of the implementation (with non-abstract methods) while leaving the rest (abstract methods) to be implemented by derived classes.
- **Inheritance**: Abstract classes cannot be instantiated on their own and must be inherited. They can contain a mix of methods with or without implementations.
- **Polymorphism**: Abstract classes allow for polymorphism. A base class reference can point to a derived class object, enabling the invocation of methods from the derived class.