# Algorithm and Data Structure
## Introduction
**Abstract data type (ADT)** is a mathematical model for data types, where a data yype is defined by its behavior (semantics) from the point of view of a user of the data. specifically in terms of possible values, possible operations on data of this type, and the behavior of these operations.

**Data structure** is a data organization, management and storage format that enables efficient access and modification. A data structure is a collection of data values, the relationships among them, and the functions or operations that can be applied to the data.

**What it's an Algorithm?**

Input - Procedure (steps to transform input to output) - Output

**Important questions when creating algorithms**
- How much time will our algorithm take for solving a problem?
- How much memory will our algorithm consume for solving a problem?

### Unsafe Code

**Unsafe code in C#** is the part of the program that runs outside the control of the Common Language Runtime (CLR) of the .NET frameworks. The CLR is responsible for all of the background tasks that the programmer doesn’t have to worry about like memory allocation and release, managing stack etc. Using the keyword “unsafe” means telling the compiler that the management of this code will be done by the programmer. Making a code content unsafe introduces stability and security risks as there are no bound checks in cases of arrays, memory related errors can occur which might remain unchecked etc.

A programmer can make the following sub-programs as unsafe:
- Code blocks
- Methods
- Types
- Class
- Struct

Need to use the unsafe code?
- When the program needs to implement pointers.
- If native methods are used.

**Syntax**

```
unsafe Context_declaration
```

**Note:** The unsafe code will not compile directly, it gives an error. Therefore, when using Visual Studio, we need to follow the given steps:
1) Go to the project properties
2) Select the build option and check the “Allow unsafe code” option.

## Sorting Algorithms
### Stable vs Unstable algorithm
An **Stable** algorithm preserves the order or records with equal keys, if not, it's **Unstable**.

![image](https://user-images.githubusercontent.com/13497579/188289683-b8611663-71fb-41e9-926a-1fb7bdc6084a.png)

### Sorting algorithms
- Bubble Sort --> Stable but slow
- Selection Sort --> Unstable but faster than bubble sort

