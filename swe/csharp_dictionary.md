[C#](csharp)
[C# Collections](csharp_collections)

---
# C# `Dictionary<TKey, TValue>`
A `Dictionary` is a collection of key-value pairs (`KeyValuePair<TKey, TValue>`) where each key must be unique. It provides fast lookups, additions, and removals using a hash table internally.

It implements:
- ✅ `ICollection` -> (`ICollection<KeyValuePair<TKey, TValue>>`).
- ✅ `IEnumerable` -> (`IEnumerable<KeyValuePair<TKey, TValue>>`).

## Common operations
1. Creating a Dictionary, adding key-value pairs and accessing key-value pairs:
```csharp
// Creating a dictionary
Dictionary<int, string> students = new Dictionary<int, string> ();

// Adding key-value pairs (in two different ways)
students.Add(1, "Keefle");
students[2] = "Yusuf";

// Accesing key-value pairs
Console.WriteLine(students[2]); // Output: Yusuf
```

2. Checking for a key:
```csharp
students.ContainsKey(2); // Returns true or false.
```

3. Iterating over a dictionary:
```csharp
foreach (var student in students)
	Console.WriteLine($"ID: {student.Key}, Name: {student.Value}");

// or foreach (KeyValuePair<int, string> in students)
```

4. Removing an key-value pair:
```csharp
students.Remove(1);
```

5. Getting a value safely with `TryGetValue`:
```csharp
if (students.TryGetValue(4, out string name))
	Console.WriteLine($"Student found: {name}");
else
	Console.WriteLine($"Student not found.");
```

6. Getting all Keys and Values:
```csharp
var studentIds = students.Keys;
var studentNames = students.Values;

foreach (int studentId in studentIds)
	Console.WriteLine(studentId);
```

7. Getting the number of key-value pairs:
```csharp
students.Count;
```