[C#](csharp)
[C# Value Types](csharp_value_types)

---
# C# `Tuple`
A `Tuple` is a data structure that allows you to store fixed-size collection of elements. In C#, a `Tuple` can hold up to 8 elements of different *types*. Tuples are **immutable** (meaning their values cannot be changed after creation).

## Common operations
```csharp
// Creating a tuple
var student = new Tuple<int, string, bool>(1, "Keefle", true);

// Accessing elements
int studentId = student.Item1;
string studentName = student.Item2;
bool studentPassedExam = student.Item3;
```
