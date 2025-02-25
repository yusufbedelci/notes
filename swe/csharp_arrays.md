[C#](csharp)

---
# C# `Array`s
An `Array` in C# is a fixed-size, zero-based collection of elements of the same type. Arrays are highly efficient when you need to store and access a large number of items. Array elements are accessed using an index, which starts from `0` (zero-indexed).

- Arrays can be [multidimensional](#multidimensional-arrays)
- You can create [arrays of arrays](#jagged-arrays).

## Common operations
### Declaration, initialization and access
- Basic array declaration and initialization:
```csharp
// An array of 5 integers where each value is by default 0.
int[] numbers = new int[5];
```

- Array initialization with values:
```csharp
var numbers = new int[] { 1, 2, 3, 4, 5 };

// Or more concisely:
int[] numbers = { 1, 2, 3, 4, 5 };
```

- Accessing and modifying individual elements:
```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
Console.WriteLine(numbers[1]) // Accessing and printing second element.
numbers[3] = 10; // Modifying the fourth element.
```

### Common methods and properties
- `.Length` -> Get number of elements in the array:
```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
Console.WriteLine(numbers.Length); // Output: 5
```

- `Array.Copy(T[], T[], int)` -> Copy elements from one array to another:
```csharp
int[] source = { 1, 2, 3 };
int[] destination = new int[3];
Array.Copy(source, destination, source.Length);
```

- `Array.Sort(T[])` -> Sorts the array elements in ascending order:
```csharp
int[] numbers = { 5, 3, 8, 1, 2 };
Array.Sort(numbers);
```

- `Array.Reverse(T[])` -> Reverses the order of elements in the array.

- `Array.Resize(T[], int)` -> Resizes the array by creating a new array and assigning it to the variable:
```csharp
Array.Resize(ref numbers, 10); // Resize numbers to 10 elements.
```

### Iterating over arrays
You can iterate through an array using the `for` and `foreach` loops.
- `for` loop:
```csharp
for (int i = 0; i < numbers.Length; i++)
	Console.WriteLine(numbers[i]);
```

- `foreach` loop:
```csharp
foreach (int number in numbers)
	Console.WriteLine(number);
```

## Multidimensional Arrays
C# supports multidimensional arrays for representing tables or grids:
```csharp
// 2D array
int[,] numbers = new int[2, 3]
{
	{ 1, 2, 3 },
	{ 4, 5, 6 }
};

// Accessing elements
numbers[1, 2]; // returns 6

// Iterating over elements
for (int i = 0; i < numbers.GetLength(0); i++) // Rows
	for (int j = 0; j < numbers.GetLength(1); j++) // Columns
		Console.Write($"{numbers[i, j]} ");
```

## Jagged Arrays
A jagged array is an array of arrays where each element (array) can have a different size:
```csharp
// Example declaration 1
int[][] numbers = new int[3][];
numbers[0] = new int[] { 1, 2 };
numbers[1] = new int[] { 3, 4, 5, 6 };
numbers[2] = new int[] { 7, 8, 9 };
```

```csharp
// Example declaration 2
int[][] numbers =
{
	new int[] { 1, 2 },
	new int[] { 3, 4, 5, 6 },
	new int[] { 7, 8, 9 }
}

// Accessing elements
numbers[2][1]; // returns 8

// Iterating over elements
foreach (var row in numbers)
	foreach (int n in row)
		Console.Write($"{n} ");
```