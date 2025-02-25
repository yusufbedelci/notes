[C#](csharp)
[C# OODP](csharp_oodp)

---
# C# Polymorphism
Polymorphism, one of the core concepts in object-oriented programming, refers to the ability of a single entity to take on multiple forms. In C#, polymorphism manifests in several ways, allowing developers to design flexible and reusable code. Two of the primary manifestations of polymorphism are method overloading and constructor overloading.

## Method overloading
Method overloading is the practice of defining multiple methods in the same scope, with the same name, but different parameters. That means different parameter numbers, types or order. This allows a class to perform a single action in different ways, depending on the arguments passed to the method.
```csharp
public class static Calculator
{
	// Method to add two integers
	public static int Add(int a, int b) => a + b;

	// Overloaded method to add three integers
	public static int Add(int a, int b, int c) => a + b + c;

	// Overloaded method to add two doubles
	public static double Add(double a, double b) => a + b;
}
```

### Ambiguous method calls
Sometimes the compiler cannot determine which method to call because the method signatures are too similar or the arguments passed can match multiple overloads. You must prevent this by ensuring each overloaded method has a clearly distinct and unambiguous signature, you might need to change the method's name or the types/order of the parameters.

## Constructor overloading
Constructor overloading is essentially similar to method overloading but applied to the constructor of a given class. This provides flexibility in object creation, allowing different sets of parameters for initializing an object.

### Constructor chaining
Constructor chaining is the practice of calling one constructor from another within the same class to reduce code duplication. This can be achieved using the `this` keyword followed by the argument list to chain constructors.

```csharp
public class Person
{
	public string Name;
	public int Age;
	public string Country;
	
	public Person(string name, int age)
    {
		Name = name;
        Age = age;
        Country = "Unknown";
    }
    
    public Person(string name, int age, string country) : this(name, age)
    {
	    Country = country;
    }
}
```
