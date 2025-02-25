[C#](csharp)
[C# Basics](csharp_basics)

---
# C# Loops
Loops are used in programming to execute a block of code repeatedly until a certain condition is met. C# provides several types of loops for different scenarios.

## The `while` loop
The `while` loop repeats a block of code as long as the specified condition is `true`. The condition is evaluated before entering the loop.
```csharp
while (condition)
{
	// Code to exectue as long as the condition is true.
}
```

## The `do-while` loop
The `do-while` loop is similar to the `while` loop, but the condition is evaluated after the execution of the loop's body. This guarantees that the loop body is executed at least once.
```csharp
do
{
	// Code to execute
} while (condition);
```

## The `for` loop
The `for` loop executes a block of code a specific number of times. It's commonly used when the number of iteration is known before entering the loop.
```csharp
for (int i = 0; i < 5; i++)
{
	Console.WriteLine(i);
}
```

## The `foreach` loop
The `foreach` loop iterates over each element in a collection (like a [List](csharp_list)). It's especially useful when you want to perform an action on each item in a collection without worrying about the structure of the collection or the number of elements.
```csharp
List<string> names = new List<string>() { "Keefle", "Yusuf" };
foreach (string name in names)
{
	Console.WriteLine(name);
}
```

## Tips and best practices
### Loop control statements
the `break` keyword can be used to exit a loop immediately and the `continue` keyword can be used to skip the current iteration and proceed to the next iteration.
### Collection modification
Avoid modifying the collection you're iterating over in a `foreach` loop as it can lead to exceptions. If you need to modify the collection consider using a `for` loop or other strategies.
### Infinite loops
Be cautious of creating infinite loops (where the condition is always `true`). Ensure that the loop's condition will eventually become `false`.
### Looping over strings
It is possible to loop over the characters of `string` as it is a collection/sequence of `char`s:
```csharp
string name = "Keefle";
foreach (char letter in name)
{
	Console.WriteLine(letter);
}
```