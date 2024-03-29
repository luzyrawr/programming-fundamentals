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
**Test Double** is any special testing object that replace the real dependencies to alter the behavior of an original object in some way.
```
                 --> Fake  
  Test Double   
                 --> Dummy --> Stub --> Spy --> Mock
```

**Interaction testing** is how an object sends messages (calls methods) to other objects. We use interaction testing when calling another object is the result of a specific unit of work.

- **Dummy:** is a test double which returns values which are either null in case of returning a reference type or close to zero in the case of structures. Dummies just do nothing inside methods which are not supposed to return anything.
- **Stub:** is a dummy which is set so that it returns predefined constant values from the methods called on the object which that stub replaces. Use stubs to drive the execution flow through specific pathways.
- **Spy:** is a stub which saves some information about the calls made on the spy. It allows to verify what argument values were passed in the methods, how many times any methods were called, in what order the methods were called.
- **Mock:** is a spy, but mock contains assertions inside itself, so a mock can cause the failure of a test.
- **Fake:** is a test double which simulates the behavior of a real dependency as close to reality as possible.

## Mocking Frameworks
Mocking Frameworks are independent of Unit Testing Frameworks. They help to automate the creation of Test Doubles.
Types of mocking frameworks: **Constrained and Unconstrained.**

- **Constrained Frameworks**
    - Cannot create test doubles for private methods or static methods.
    - Generate code at runtime that inherits and overrides interfaces or base classes.
    - You can create test dobules only for the code for which you can create test doubles manually.
    - Examples: NSubstitute, Moq, RhinoMock.

- **Unconstrained Frameworks**
    - Can create test double for literally anything.
    - Generate code at runtime. Based on the profiling APIs. These APIs provide events for anything that happens during CLR code execution.
    - Example: Typemock Isolator.

## Notes 👀
- **Good unit tests are just regular clients of the production code**, it can call only public members.
- Tests which need to create **test doubles for private methods are very suspicious.**
- Most likely, **if you need to cheat the public API somehow, you have problems with the desing.** You need to refactor the production code to enable unit testing.

## Best Practices
### What makes a Valuable Test?
- Has a high chance of catching a regression error.
- Has a low chance of producing a false positive.
- Provides fast feedback.
- Has low maintenance cost.

### When to write Mocks
- Unit tests should not test the correctness of interaction between domain objcts. Such tests experience lots of false positives and worse maintainability since they usually involve the writing of mocks.
- Always choose to use interaction testing only as the last option. Try to rely on tests that verify state or returning values, because so many things become much more complicated by having interaction tests.

### One-Assert-Per-Test
- Test one aspect/behaviour in each test.

### Characteristics of Good Unit Testing
- Trustworthiness
- Maintainability
- Readability

### What to Avoid
- Avoid control flow operators (switch, if, else, foreach, for, while). Having flow operators in a unit test is a smell wich shows that your unit test is to complex, and most likely you need to refactor into more tests.
- Avoid Duplication. Avoid repetitive logic.
- Avoid setting up Test Doubles in the [SetUp] method. Create mocks and stubs in each test.
- Avoid ordered tests
  - Creates temporal coupling between unit tests.
  - Adding a new test to a particular order, you need to think about when that test should run.
  - Ordered tests are slower.
  - Ordered tests are hard to maintain.
- Over specification
  - Assert purely internal state in an object under test.
  - User more than une mock in a single test.
  - Use both stubs and mocks in a single test.
  - Assert specific call orders or exact string matches when it isn't required.

### Independency and Isolation
- Test should not be dependent on each other.
