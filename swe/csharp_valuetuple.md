[C#](csharp)
[C# Value Types](csharp_value_types)

---
# C# `ValueTuple`
A `ValueTuple` is a lightweight, **mutable**, and more efficient alternative to the [`Tuple`](csharp_tuple) type. The elements of a `ValueTuple` can be named and provides better performance in many cases.

## Common operations
```csharp
// Creating a ValueTuple with unnamed elements
var teacher = (1, "Keefle", true);

// Creating a ValueTuple with named elements
var student = (Id: 1, Name: "Yusuf", PassedExam: false);

// Accessing named elements
int studentId = student.Id;
string studentName = student.Name;
bool studentPassedExam = student.PassedExam;

// Modifying elements
student.PassedExam = true;
```
