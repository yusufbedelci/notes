[C#](csharp)
[C# Basics](csharp_basics)

---
# C# Conditional statements
Conditional statements allow you to execute different code blocks based on certain conditions. They are fundamental for decision-making in programs.

## `if`, `else if`, `else` statements
These are the standards statements in most programming languages and are used to execute a block of code if a given condition is `true`.

```csharp
int age = 22;
if (age > 0 && age <= 12)
{
	// code to execute if age is less than or equal to 12
}
else if (age < 18)
{
	// code to execute if age is greater than 12 or less than 18
}
else
{
	// code to execute if age is greater than 18
}
```

## Ternary operator
The ternary operator is a shorthand for the `if`-`else` statement:
```csharp
string accountStatus = (accountBalance >= 0) ? "good standing" : "overdrawn";
```

## The `switch` statement
The `switch` statement simplifies the code when you have multiple conditions to check. It tests a variable against a list of values which are called `case`s, and executes the block of code corresponding to the first matching case.

```csharp
switch (dayOfWeek)
{
	case DayOfWeek.Saturday:
	case DayOfWeek.Sunday:
		// Code to execute if it's weekend.
		break;

	default:
		// Code to execute if it's a weekday.
		break;
}
```
Tip: Always include a `default` case to handle unexpected values. Each case ends with a `break` to prevent fall-through (except if explicitly desired).
Note:

## `switch` expressions
In C# 8.0 and later there is a more concise and functional version of the `switch` statement which returns a value based on a matched pattern and is particularly useful when assigning a value to a variable or when you need an expression as a part of a bigger operation.

```csharp
var description = dayOfWeek switch {
	DayOfWeek.Saturday => "Weekend",
	DayOfWeek.Sunday => "Weekend",
	_ => "Weekday" // Default case.
};
```
Tip: `switch` expressions provide a more concise syntax and will enforce that all possible cases are handled (exhaustiveness).
NOTE: If a default case is missing and none of the defined cases match, the compiler will generate an error.