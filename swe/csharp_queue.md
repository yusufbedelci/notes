[C#](csharp)
[C# Collections](csharp_collections)

---
# C# `Queue<T>`
A `Queue<T>` is a collection type that follows the **First-In First Out (FIFO)** principle. This means that the first item added is the first one to be removed, like a queue of people waiting in line.

It implements:
- ✅ `ICollection` -> (`ICollection<T>`).
- ✅ `IEnumerable` -> (`IEnumerable<T>`).

## Common methods and properties
- `.Enqueue(T item)` -> Adds an element to the back of the queue.
- `.Dequeue()` -> Removes and **returns** the element at the front of the queue.
- `.Peek()` -> Returns the element at the front of the queue **without** removing it.
- `.Contains(T item)` -> Checks if an element is in the queue.
- `.Clear()` -> Removes all elements from the queue.
- `.Count` -> Gets the number of elements in the queue.