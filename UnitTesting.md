# Unit Testing
## Naming Conventions
### Recommendations when naming unit testing projects.
**Naming Pattern:** ProjectNameUnderTest.Tests

**Example:** Business.Tests

### Recommendations when naming unit testing classes.
**Naming Pattern:** ClassNameUnderTestTests

**Example:** SerialPortParserTests

### Recommendations when naming unit testing methods.

**Naming Pattern:** "UnitUnderTest_Scenario_ExprectedOutcome"

**Example:** void ParsePort_COM1_Returns1()

- **UnitUnderTest:** unit of work that we are testing, it could also be a function under test or something more abstract like use-cases, for exmple: RemoveUser.
- **Scenario:** Scenario of the testing proces, reflects the conditions under which the unit is going to be tested. We can use the arguments passed in the function under test, it could also be a more abstract scenario, for example: InvalidStringFormat.
- **ExpectedOutcome:** the expected behavior. There are three ways of naming this part, depending on the outcome of the function under test:
    - **ReturnsValue:** for example ReturnZero.
    - **ChangesState or SetState:** for example SetNumberToZero. Recomended when the outcome of the test can be observed via its public properties.
    - **CallsDependency:** for example CallsProcessingGateway. Recomended when we validate the correctness of interactions between objects.

## Arrange-Act-Assert
Almost all test consist of thre steps: Arrange, Act and Assert.
- **Arrange:** set up the system under test.
- **Act:** calling of the methods.
- **Assert:** verify the correctness of the behavior by assertions.

## Parametrized Tests
Use TestCase attribute. Example:

```
[TestCase(1,40)]
public void test_parametrized(int value, int expected)
{
    ...
}
```

## SetUp and TearDown Attributes
- `[Setup]` is an attribute for methods to define that it will run before every test.
- `[TearDown]` is an attribute for methods to define that it will run after every test.

## OneTimeSetUp and OneTimeTearDown Atrributes
- `[OneTimeSetUp]` is an attribute for methods to define that it will run before all the test of the Assembly or Namespace.
- `[OneTimeTearDown]` is an attribute for methods to define that it will run after all the test of the Assembly or Namespace.

## Testing Exceptions
Example:
```
public void test_throwException()
{
   TestDelegate action = () => Class.method(0);
   Assert.Throws<FormatException>(action);
}
```

## Group Tests
```
[Category("GroupName")] attribute
```

## Ignore Tests
```
[Ignore] attribute
```

## Code Coverage
It's a metric that shows the amount of code covered by tests. Only available in VS Enterprise :(

## Test Doubles
Test Double is any special testing object that replace the real dependencies to alter the behavior of an original object in some way.
