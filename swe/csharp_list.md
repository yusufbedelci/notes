[C#](csharp)
[C# Basics](csharp_basics)
[C# Collections](csharp_collections)

---
# C# `List<T>`
The `List<T>` class is a part of the `System.Collections.Generic` namespace and represents a strongly typed list of objects that can be accessed by index. It provides methods to search, sort, and manipulate lists.

## Adding items
The `.Add(T item)` method adds items to the end of the `List`.
```csharp
List<int> numbers = new List<int>();
numbers.Add(1); // List numbers now contains {1}
```

## Removing items
The `.Remove(T item)` method removes the first occurrence of a specific object from the `List`.
```csharp
numbers.Remove(1); // Removes 1 from the list.
```
Tip: this method will return a boolean value to indicate whether an item was successfully removed or not. It will return `false` if the item was not found in the list, or the operation failed.

There is also the `.RemoveAt(int index)` method which removes the element at the specified index of the `List`.
```csharp
numbers.RemoveAt(0); // Removes the first item.
```

## Counting items
The `.Count` property gets the number of elements contained in the `List`.
```csharp
int numberOfElements = numbers.Count;
numbers.RemoveAt(numberOfElements - 1); // Removes the last item from the list.
```

## Tips and best practices
### List initialization
You can initialize a list with elements using collection-initializer syntax:
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4 };
```

### Accessing elements
Elements of a list can be accessed by their index. List indices are zero based.
```csharp
int firstNumber = numbers[0];
```

### Checking for existence
You can check whether the `List` contains a given value/item using the `.Contains(T item)` method.
```csharp
numbers.Contains(2); // returns true if numbers List contains the int 2.
```

### Capacity vs. Count
`Capacity` is the number of elements that the List can store before resizing is required, while `Count` is the number of elements actually in the `List`. Adding elements beyond the current capacity automatically resizes the internal array, which can be a costly operation. If the final size of the list is known in advance, consider setting the initial capacity.
```csharp
List<int> numbers = new List<int>(9); // predefining the capacity of the list.
```