[C#](csharp)
[C# Collections](csharp_collections)

---
# C# `Stack<T>`
A `Stack<T>` is a collection type that follows the **Last-In First Out (LIFO)** principle. This means that the most recently added item is the first one to be removed, like a stack of books.

It implements:
- ✅ `ICollection` -> (`ICollection<T>`).
- ✅ `IEnumerable` -> (`IEnumerable<T>`).

## Common methods and properties
- `.Push(T item)` -> Adds an element to the stack.
- `.Pop()` -> Removes and **returns** the element at the top of the stack.
- `.Peek()` -> Returns the element at the top of the stack **without** removing it.
- `.Contains(T item)` -> Checks if an element is in the stack.
- `.Clear()` -> Removes all elements from the stack.
- `.Count` -> Gets the number of elements in the stack.