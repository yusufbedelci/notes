[C#](csharp)

---
# C# LINQ
## Overview
LINQ stands for *Language Integrated Query* and is a set of tools in C# that allows you to query collections like arrays, lists, or databases using a syntax integrated into C#. LINQ can be used with objects that implement `IEnumerable<T>` or `IQueryable<`T>`.

Queries can be written in both query syntax or (lambda) method syntax:
```csharp
// Query syntax
var query = from item in collection
			where condition
			select item;
```

```csharp
// Method syntax
var query = collection
			.Where(condition)
			.Select(item => item);
```

## Basic LINQ features
### Selecting Data
Selecting data means transforming or picking specific elements from a collection. We can use `select` / `.Select()` to *project* data into a new shape.

```csharp
var students = new List<Student>
{
	new Student { Id = 1, Name = "Keefle", Age = 24 },
	new Student { Id = 2, Name = "Yusuf", Age = 23 },
	new Student { Id = 3, Name = "Bob", Age = 20 },
};

var names = students.Select(student => student.Name);

Console.WriteLine(string.Join(", ", names)); // Output: Keefle, Yusuf
```

```csharp
// using query syntax
var names = from student in students
			select student.Name;
```

### Filtering Data
Filtering data means selecting elements based on a condition. `where` / `.Where()` is used for filtering.

```csharp
var studentsOver21 = students.Where(student => student.Age > 21)
							 .Select(student => student.Name);

Console.WriteLine(string.Join(", ", studentsOver21s)); // Output: Keefle, Yusuf
```

```csharp
// using query syntax
var studentsOver21 = from student in students
					 where student.Age > 21
					 select student.Name;
```

### Grouping Data
Grouping data means categorizing elements based on a specific property. LINQ's `.GroupBy()` method or `group` `by` keywords can be used to group elements in a collection.

```csharp
var groupedByAge = students.GroupBy(student => student.Age);

foreach (var ageGroup in groupedByAge)
	foreach (var student in ageGroup)
		Console.WriteLine(student.Name);
```

```csharp
// using query syntax
var groupedByAge = from student in students
				   group student in student.Age;
```

### Sorting Data
You can sort data using `.OrderBy()` / `orderby` (ascending) and `.OrderByDescending()`/ `orderby` `descending`.

```csharp
// method syntax
var sortedStudentsAsc = students.OrderBy(student => student.Name);
var sortedStudentsDes = students.OrderByDescending(student => student.Name);
```

```csharp
// query syntax
var sortedStudentsAsc = from student in students
						orderby student.Name
						select student;

var sortedStudentsDes = from student in students
						orderby student.Name descending
						select student;
```
