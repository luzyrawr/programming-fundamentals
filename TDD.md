# TDD - Test-Driven Development
Is the approach of writing tests ahead of the production code.

Unit tests are specifications of what the code should do. Writing unit tests in the first place, allow us to implement only that production code to satifies the unit tests.

**Red \ Green \ Refactor** are the three steps of TDD. We first write a **failing test**, then write the production code to make the **test pass** and then **refactor** both the production and testing code.

## Three Main TDD Techniques
- **Faking:** implies returning a constant and gradually replace constants with variables until you have the real code.
- **Triangulation:** is the process of affing test cases until the right way of implementation starts to emerge.
- **Obvious IMplementation:**
