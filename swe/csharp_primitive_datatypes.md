[C#](csharp)
[C# Basics](csharp_basics)

---
# Primitive datatypes
## Strings and Characters
**Strings** (`string`) represent a sequence of characters are used to store textual data:
- Initialization -> `string name = "Keefle";`.
- Concatenation -> `string fullName = "Keefle " + "Usta";`.
- Interpolation -> `string greeting = $"Hello, {fullName}!";`.
- Methods/properties -> `.Length`, `.Substring()`, `.Replace()`, `.ToUpper()`, `.ToLower()`.

a **Character** (`char`) represents a single character:
- Initialization -> `char letter = 'A';`.
- Escape Sequences -> `\n` for new line, `\t` for tab.
- Methods -> `char.IsDigit(a)`, `char.IsLetter(b)`.
- Tip -> Char values are based on ASCII, and numerical operations can be performed on them.

## Numerical types
**Integers** (`int`) are whole numbers:
- Initialization -> `int age = 22`;
- Range -> -2,147,483,648 to 2,147,483,647.
- Usage -> Counting items, indexing arrays, loops.
- Tip -> Use `long` for larger values.

**Double** `double` used for floating-point numbers:
- Precision -> Approximately 15-16 digits.
- Usage -> Scientific calculations, digital measurements (for example game development).
- Tip -> Use `decimal` for financial or real world calculations due to higher precision.

- The digit separator `_` can be used with any numerical types to enhance readability like so: `int million = 1_000_000;`

## Boolean type
**Boolean** (`bool`) represents a true or false:
- Initialization -> `bool isDone = true;`
- Usage -> Conditional statements and flags.

## Type conversion
There is implicit and explicit type conversion in C#. Implicit type conversion can be done without explicit casting, and will be allowed by the compiler. This is usually when you're converting a type into another where no data can be lost:

```csharp
int height = 176;
long newHeight = height;
double evenNewerHeight = height;
```

Explicit type conversion requires a cast operator and must be done manually by the programmer. This is usually because of the chances of data loss. There are a variety of ways to perform explicit type conversion:

Type casting:
```csharp
double pi = 3.14;
int intPi = (int)pi; // intPi will be 3, losing the decimal part.
```

Using the `Convert` class:
```csharp
int age = Convert.ToInt32("22");
```

Using `.Parse()` methods:
```csharp
int houseNumber = int.Parse("123");
```

Using `.TryParse()` methods, which return a boolean with the result of whether the parse operation was successful:
```csharp
bool result = int.TryParse("123", out int houseNumber);
```