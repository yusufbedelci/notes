[C#](csharp)
[C# OODP](csharp_oodp)

---
# C# Inheritance
Inheritance is a fundamental concept in object-oriented programming that allows a class to inherit properties and methods from another class. In C#, inheritance is used to promote code reuse, implement polymorphism, and establish a relationship between classes based on a hierarchy.

## Base and derived classes
- **Base Class**: also known as the parent or superclass, it provides common properties and methods that can be inherited.
- **Derived Class**: also known as the child or subclass, it inherits from the base class, can add new properties and methods, and override existing ones.

Derived classes extend the functionality of base classes by adding new properties, methods or overriding existing one:
```csharp
public class Animal // Base class
{
	public void Eat() => Console.WriteLine("Eating...");
}

public class Dog : Animal // Derived class
{
	public void Bark() => Console.WriteLine("Barking...");
}
```

## Constructor inheritance
Derived classes can also call base class constructors to ensure the base class is correctly initialized:
```csharp
public class Animal
{
	public string Name;
	public Animal(string name)
	{
		Name = name;
	}
}

public class Dog : Animal
{
	public string Breed;
	public Dog(string name, string breed) : base(name)
	{
		Breed = breed;
	}
}
```

## Looping through objects of a base and derived class
You can store instances of derived classes in collections of the base class type and loop through them, treating them polymorphically:
```csharp
List<Animal> animals = new List<Animal>
{
	new Animal("Bear");
	new Dog("Buddy");
}

foreach (var animal in animals)
{
	Console.WriteLine(animal.Name);
	if (animal is Dog dog)
		dog.Bark();
}
```

## Casting and Type checking
### Casting to base
Derived class instances can be cast to their base class type to only access base class members.
```csharp
Dog snoop = new Dog();
Animal snoopie = snoop; // will cast snoop from Dog to Animal.
snoopie.Eat(); // OK
// snoopie.Bark(); // Compile-time error
```
### Using the `is` keyword
The `is` keyword checks if an object is of a specified type, which is useful for type checking before performing operations specific to that type.
```csharp
Animal animal = new Dog();
if (animal is Dog)
	Console.WriteLine("It's a Dog!");
else
	Console.WriteLine("It's not a Dog.");
```
### Using the `as` keyword
The `as` keyword performs a safe cast. If the cast fails (i.e. the object is not of the target type), it returns `null` instead of throwing an exception.
```csharp
Animal animal = new Animal();
Dog dog = animal as Dog; // Safe cast to Dog, will be null if animal is not a Dog
if (dog != null)
	dog.Bark();
else
	Console.WriteLine("The cast to Dog failed.");
```

## Virtual methods and Override
Virtual methods are methods that can be overridden in the derived class. To do this you need to define the given method with a `virtual` keyword, and then in the derived class you can use the `override` keyword to override it.
```csharp
public class Animal
{
	public virtual void MakeSound() => Console.WriteLine("Some sound...");
}

public class Dog : Animal
{
	public override void MakeSound() => Console.WriteLine("Bark");
}
```

Derived classes can also call an overridden method from the base class using the `base` keyword.
```csharp
public class Dog : Animal
{
	public override void Eat()
	{
		base.Eat();
		Console.WriteLine("Dog is eating.");
	}
}
```

## Overriding `Object` class methods
The `Object` class is the ultimate base class for all classes in C#. It contains certain virtual methods by default like `.ToString()` that can be overridden for custom behavior.
```csharp
public class Animal
{
	public string Name { get; set; }
	public override string ToString() => $"Animal: {Name}";
}
```

## Shadowing inherited members with `new` keyword
The `new` keyword in derived classes hides inherited members from the base class which is useful when overriding is not intended:
```csharp
public class BaseClass
{
	public void Method() => Console.WriteLine("Base");
}

public class DerivedClass : BaseClass
{
	public new void Method() => Console.WriteLine("Derived");
}
```