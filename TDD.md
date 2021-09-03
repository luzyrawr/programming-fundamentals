# TDD - Test-Driven Development
Is the approach of writing tests ahead of the production code.

Unit tests are specifications of what the code should do. Writing unit tests in the first place, allow us to implement only that production code to satifies the unit tests.

**Red \ Green \ Refactor** are the three steps of TDD. We first write a **failing test**, then write the production code to make the **test pass** and then **refactor** both the production and testing code.

## Three Main TDD Techniques
- **Faking:** implies returning a constant and gradually replace constants with variables until you have the real code.
- **Triangulation:** is the process of affing test cases until the right way of implementation starts to emerge. Usually, two or three cases are enough to stop triangulation. Faking and Triangulation leads to the implementacion when the way of generalization becomes obvious.
- **Obvious Implementation:** if the right implementation is obvious you can skip faking and triangulation. Often the obvious implementation fails at edge cases.

# Notes 👀
- Write as many tests as possible before approaching the core functionality. Test all the edge cases: nulls, empty strings or objects, maximum values, all the cases which have to cause exceptions being thrown.
- Write tests exactly in the following order: exceptional, degenerate and ancillary.
  - Degenerative cases are those which cause the core functionality to do "nothing".
  - Ancillary behaviors are those which support the core functionality.
