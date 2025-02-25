[C#](csharp)
[C# Basics](csharp_basics)

---
# Random (numbers)
We have the `System.Random` class to generate pseudo-random numbers in C#.
## Unseeded instance
Each time you create a new unseeded instance, it's seeded based on the system clock.
```csharp
Random rnd = new Random();
int randomInt = rnd.Next(); // generates a random (non-negative) integer
int randomInt2 = rnd.Next(10); // generates a random integer from 0 to 9
int randomInt3 = rnd.Next(5, 10); // generates a random integer from 5 to 9
double randomDouble = rnd.NextDouble() // generates a random double between 0.0 and 1.0
```
## Seeded instance
When using a seeded instance it will ensure the reproducibility of the random numbers which is useful for testing purposes.
```csharp
Random rnd = new Random(123);
```