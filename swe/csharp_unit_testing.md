[C#](csharp)
[C# Testing](csharp_testing)

---
# C# Unit Testing

## Best Practices in Unit Testing
- ✅ **Keep tests isolated** -> Each test should run independently.
- ✅ **Use meaningful test names** -> E.g. `CalculateTotal_ShouldReturnCorrectSum`.
- ✅ **Follow Arrange-Act-Assert (AAA) pattern**.
- ✅ **Use `Theory` for data-driven tests** instead of duplicate `Fact` tests.
- ✅ **Mock dependencies** -> Use `Moq` or `FakeItEasy` for dependency injection.
- ✅ **Run tests frequently** -> Ensure tests execute on every commit (CI/CD).