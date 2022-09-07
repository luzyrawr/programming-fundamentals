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
### In-place algorithm
Is an algorithm that does not need an extra space and produces an output in the same memory that contains the data by transforming the input ‘in-place’. However, a small constant extra space used for variables is allowed.

### Stable vs Unstable algorithm
An **Stable** algorithm preserves the order or records with equal keys, if not, it's **Unstable**.

![image](https://user-images.githubusercontent.com/13497579/188289683-b8611663-71fb-41e9-926a-1fb7bdc6084a.png)

### Sorting algorithms
| Sorting Algorithm | Hint to remember the algorithm | Stable/Unstable | In-Place | Iteration or Recursion | Speed | Comments
|--|--|--|--|--|--|--|
| Bubble Sort | Compare elements until reach the wall | Stable | In-Place | Iteration |Slow | The slowest algorithm |
| Selection Sort | Compares the largest element | Unstable | In-Place | Iteration | Slow | Faster than bubble sort |
| Insertion Sort | Like swapping cards in a hand | Stable | In-Place | Iteration | Slow | Faster if the array is almost ordered |
| Shell Sort | Based on Insertion Sort, makes a presort by comparing elements separed by a gap | Unstable | In-Place | Iteration | Fast | Easy to implement, improve of Insertion Sort |
| Merge Sort | Divide and Conquer, splitting by half and merging | Stable | Not in-place | Recursion | Fast | Uses a lot of memory but is a fast competitor |
| Quick Sort | Divide and Conquer, splitting by pivot, compares to pivot and swap | Unstable | In-place | Recursion | Fast | Best performing algoritms |

## Linked Lists
### Node
A **node** is a basic build block of many data structures. A **node** serves to functions:
1) Data container
2) Pointer to the next node

### Linked List
**Linked List** is an abstract data type, which allows to build chains of elemnents and provide the following key elements and operations:
- Reference to Head (first node)
- Reference to Tail (last node)
- Operations:
  - Add
  - Remove
  - Find
  - Enumerate

There are two major types of linked lists:
- Singly Linked List: each node has a reference to the next node
- Doubly Linked List: each node has a reference to the previous node and the next node

## Stack
**Stack** is an abstract data type, it has a linear data structure which follows a particular order in which the operations are performed. The order may be LIFO(Last In First Out). It provides the following operations:
- Push - add item to the top
- Pop - remove the top item
- Peek - get the top item without removing

Can be implemented with array or linked list.

## Queues
**Queue** is an abstract data type, it has a linear data structure which follows a particular order in which the operations are performed. The order may be FIFO(First In First Out). It provides the following operations:
- Enqueue - add item to the end of the queue
- Dequeue - remove an item at the front of the queue
- Peek - get the top item at the front of the queue without removing

Can be implemented with array or linked list.
