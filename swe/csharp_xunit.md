[C#](csharp)
[C# Unit Testing](csharp_unit_testing)

---

# C# xUnit
**xUnit** is a modern, open-source unit testing framework for .NET applications. It is widely used for testing ASP.NET Core, C# libraries, and console applications. Compared to older frameworks like NUnit and MSTest, xUnit is more flexible, lightweight, and aligned with modern .NET development practices.

## Setting up a test project & running tests
To create a test project in .NET Core:

1. Install xUnit & Test SDK:
```csharp
dotnet new xunit -n MyProject.Tests
cd MyProject.Tests
dotnet add package Microsoft.NET.Test.Sdk
dotnet add package xunit
dotnet add package xunit.runner.visualstudio
```

2. Ensure test discovery:
```csharp
dotnet test
```

## Test attributes in xUnit
| Attribute           | Description                                                                |
| ------------------- | -------------------------------------------------------------------------- |
| `[Fact]`            | Marks a **standard** test method.                                          |
| `[Theory]`          | Marks a **parameterized test**. Requires `[InlineData]` or `[MemberData]`. |
| `[InlineData(...)]` | Supplies test data for a `[Theory]` test.                                  |
| `[ClassData]`       | Supplies test data from a class implementing `IEnumerable<object[]>`.      |
| `[MemberData]`      | Uses data from a static property or method.                                |

```csharp
public class MathTest
{
	[Fact]
	public void Add_Returns_CorrectSum()
	{
		Assert.Equal(5, 2 + 3);
	}

	[Theory]
	[InlineData(2, 3, 5)]
	[InlineData(5, 5, 10)]
	[InlineData(0, 1, 1)]
	public void Add_ParameterizedTest(int a, int b, int expected)
	{
		Assert.Equal(expected, a + b);
	}
}
```

## Asserts in xUnit
xUnit provides various `Assert` methods for test validation:

| Assert Method             | Description                                 |
| ------------------------- | ------------------------------------------- |
| `Assert.Equal(a, b)`      | Checks if `a == b`.                         |
| `Assert.NotEqual(a, b)`   | Checks if `a != b`.                         |
| `Assert.True(condition)`  | Checks if `condition` is `true`.            |
| `Assert.False(condition)` | Checks if `condition` is `false`.           |
| `Assert.Null(object)`     | Checks if `object` is `null`.               |
| `Assert.NotNull(object)`  | Checks if `object` is not `null`.           |
| `Assert.Throws<T>(...)`   | Verifies an exception of type `T`is thrown. |
