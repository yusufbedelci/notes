[C#](csharp)

---

# C# Lambdas and Higher-Order Functions

## Lambda basics
In C#, **lambdas** (also known as **anonymous functions**) allow you to define inline functions without a name. They are commonly used with delegates and LINQ.
```csharp
Func<int, int> square = x => x * x;
```
In the code snippet above:
- `Func<int, int>` is a delegate that represents taking an int and returning an int.
- `x => x * x` is a lambda expression.

### Delegates
- `Func<T, TResult>` is used when the function returns a value.
- `Action<T>` is used when the function returns nothing (`void`).

```csharp
Action<string> greet = name => Console.WriteLine($"Hello, {name}!");
greet("Alice"); // Output: Hello, Alice!
```

### Additional information
- Lambdas can take multiple parameters like this:
```csharp
Func<int, int, int> add = (x, y) =>  x + y;
Console.WriteLine(add(32, 23)); // Output: 55
```

- A function can return a lambda, meaning it returns another function:
```csharp
static Func<int, int> CreateMultiplier(int factor)
{
	return x => x * factor;
}

Func<int, int> doubleIt = CreateMultiplier(2);
Console.WriteLine(doubleIt(5)); // Output: 10

Func<int, int> tripleIt = CreateMultiplier(3);
Console.WriteLine(tripleIt(5)); // Output: 15
```

- Curried lambdas -> currying is the process of breaking down a function that takes multiple parameters into a series of nested functions, each taking a single parameter:
```csharp
Func<int, Func<int, int>> curriedAdd = x => y => x + y;

Func<int, int> addFive = curriedAdd(5);
Console.WriteLine(addFive(10)); // Output: 15
Console.WriteLine(addFive(5)); // Output: 10
```

## Higher-Order Functions (HOFs)
A higher-order function is a function that takes another function as a parameter or returns a function.

Example with a `Func` delegate:
```csharp
static void ApplyToEach(int[] numbers, Func<int, int> operation)
{
	foreach (var num in numbers)
		Console.WriteLine(operation(num));
}

int[] numbers = { 1, 2, 3, 4 };
ApplyToEach(numbers, x => x * x); // Squares each number
ApplyToEach(numbers, x => x + 10); // Adds 10 to each number
```

Example with an `Action` delegate:
```csharp
static void ProcessNumbers(int[] numbers, Action<int> operation)
{
	foreach (var num in numbers)
		operation(num);
}

int[] numbers = { 1, 2, 3 };
ProcessNumbers(numbers, n => Console.WriteLine(n * 2)); // doubles and prints each number
```