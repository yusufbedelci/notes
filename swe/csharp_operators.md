[C#](csharp)
[C# Basics](csharp_basics)

---
# C# Operators
Operators in C# are special symbols that perform operations on operands. They are fundamental in constructing expressions and performing calculations or comparisons.

## Assignment operator
Assigns the value on the right to the variable on the left (`=`).
```csharp
int x = 5;
```

## Arithmetic operators
Operators to perform mathematical operations.
- Operators:
	- `+` -> addition.
	- `-` -> subtraction.
	- `*` -> multiplication.
	- `/` -> division.
	- `%` -> modulus.
- Tip: Mind integer division, dividing two integers truncates the decimal part.

## Relational operators
Operators to compare two values or expressions.
- Operators:
	- `==` -> equal to.
	- `!=` -> not equal to.
	- `>` -> greater than.
	- `<` -> less than.
	- `>=` -> greater than or equal to.
	- `<=` -> less than or equal to.
- Tip: When comparing objects use `.Equals()` method, and when comparing values use `==`.

## Boolean logical operators
Operators to combine or invert boolean expressions.
- Operators:
	- `&&` -> logical AND.
	- `||` -> logical OR.
	- `!` -> logical NOT.
- Short-circuiting: `&&` and `||` stop evaluating as soon as the result is determined.

## Operator precedence
Operator precedence defines the order in which operators are evaluated in an expression.
- Hierarchy:
	1. Parentheses -> `()`.
	2. Unary operators -> `!`, `++`, `--`.
	3. Multiplication, division, and modulus -> `*`, `/`, `%`.
	4. Addition/Subtraction -> `+`, `-`.
	5. Relational operators -> `<`, `>`, `<=`, `>=`.
	6. Equality operators -> `==`, `!=`.
	7. Logical AND -> `&&`.
	8. Logical OR -> `||`.
- Associativity: Assignment operators are right-associative, meaning that they are evaluated from right-to-left, and every other operator is left-associative.