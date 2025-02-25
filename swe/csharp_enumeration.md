[C#](csharp)

---
# C# Enumeration (`enum`)
An `enum` is a special "class" in C# that represents a collection of constants, often used to represent a set of related values.

## `enum` Declaration & Initialization
An `enum` (short for enumeration) defines a set of named constants. Each constant is assigned an underlying value (typically an integer by default, but it can be any integral type).

Declaration:
```csharp
enum DayOfWeek
{
	Monday, // 0
	Tuesday, // 1
	Wednesday, // 2
	Thursday, // 3
	Friday, // 4
	Saturday, // 5
	Sunday // 6
}
```
In the example above `DayOfWeek` is an `enum` with 7 members, each representing a day of the week. By default the first member `Monday` is assigned the value `0`, and each subsequent member gets an incremented value.

Explicit initialization:
```csharp
enum DayOfWeek
{
	Monday = 1,
	Tuesday = 2,
	Wednesday = 3,
	Thursday = 4,
	Friday = 5,
	Saturday = 6,
	Sunday = 7
}
```

## Using a `switch` with `enum`
You can use an `enum` in a `switch` statement to perform different actions based on the value of the enum:

```csharp
DayOfWeek today = DayOfWeek.Monday;

switch (today)
{
	case DayOfWeek.Saturday:
	case DayOfWeek.Sunday:
		Console.WriteLine("It's the weekend!");
		break;
	case DayOfWeek.Monday:
		Console.WriteLine("It's monday!");
		break;
	default:
		Console.WriteLine("It's a weekday!");
		break;
}
```

## Iterating over an `enum`
You can loop through all the members of an `enum` using `Enum.GetValues()`. This is useful if you want to process or display all the enum values.
```csharp
foreach (DayOfWeek day in Enum.GetValues(typeof(DayOfWeek)))
	Console.WriteLine(day);
```

## Parsing an `enum` member
If you have a string representation of an enum member (e.g. `"Monday"`), you can convert it back into its enum value using `Enum.Parse()` or `Enum.TryParse()`:

```csharp
// With Enum.Parse()
string input = "Monday";
DayOfWeek day = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), input);
```

```csharp
/// With Enum.TryParse()
string input = "Monday";
result = Enum.TryParse(input, out DayOfWeek day) // returns true or false
```

## Converting to and from `enum`
You can easily convert an `enum` to its underlying numeric value or vice versa.

`enum` to integer:
```csharp
DayOfWeek today = DayOfWeek.Monday;
int value = (int)today; // returns 1
```

integer to `enum`:
```csharp
int dayValue = 3
DayOfWeek day = (DayOfWeek)dayValue; // returns Wednesday
```

## `enum` member descriptions
We can add descriptions to `enum` members using the `Description` attribute from `System.ComponentModel`:

```csharp
enum DayOfWeek
{
	[Description("The first day of the week")]
	Monday,
	[Description("The second day of the week")]
	Tuesday,
	[Description("The third day of the week")]
	Wednesday,
	[Description("The fourth day of the week")]
	Thursday,
	[Description("The fifth day of the week")]
	Friday,
	[Description("The sixth day of the week")]
	Saturday,
	[Description("The seventh day of the week")]
	Sunday
}
```