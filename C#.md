# C# Basic Concepts
## String Interpolation

Another option of string concatenation, is string interpolation, which substitutes values of variables into placeholders in a string. Note that you do not have to worry about spaces, like with concatenation:

```
string firstName = "John"; 
string lastName = "Doe"; 
string name = $"My full name is: {firstName} {lastName}"; 
Console.WriteLine(name); //Output: My full name is: John Doe
```

## Break and Continue

You have already seen the **break** statement used in an earlier chapter of this tutorial. It was used to "jump out" of a switch statement.
The **break** statement can also be used to jump out of a loop.
This example jumps out of the loop when i is equal to 4:

```
for (int i = 0; i < 10; i++)  
{ 
  if (i == 4)  
  { 
    break; 
  } 
  Console.WriteLine(i); 
}
```

The **continue** statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.
This example skips the value of 4:

```
for (int i = 0; i < 10; i++)  
{ 
  if (i == 4)  
  { 
    continue; 
  } 
  Console.WriteLine(i); 
}
```

## Arrays

```
string[] cars;

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
int[] myNum = {10, 20, 30, 40};

Array.Sort(cars);
Array.Sort(myNum);
```

## Enums

If values are not assigned to enum members, then the compiler will assign integer values to each member starting with zero by default. The first member of an enum will be 0, and the value of each successive enum member is increased by 1.

```
enum WeekDays
{
    Monday,     // 0
    Tuesday,    // 1
    Wednesday,  // 2
    Thursday,   // 3
    Friday,     // 4
    Saturday,   // 5
    Sunday      // 6
}
```

You can even assign different values to each member.

```
enum Categories
{
    Electronics = 1,  
    Food = 5, 
    Automotive = 6, 
    Arts = 10, 
    BeautyCare = 11, 
    Fashion = 15,
    WomanFashion = 15
}
```

Access and convert enums

```
using System; 
namespace MyApplication 
{ 
  enum Level 
  { 
    Low,     //0
    Medium,  //1
    High     //2
  } 
  class Program 
  { 
    static void Main(string[] args) 
    { 
      Level myVar = Level.Medium; 
      Console.WriteLine(myVar);               //Output: Medium
      Console.WriteLine((int) Level.Medium);  //Output: 1
      Console.WriteLine((int) myVar);         //Output: 1
    } 
  } 
}
```

## Struct

In C#, **struct** is the value type data type that represents data structures. It can contain a parameterized constructor, static constructor, constants, fields, methods, properties, indexers, operators, events, and nested types.

struct can be used to hold small data values that do not require inheritance, e.g. coordinate points, key-value pairs, and complex data structure.

```
struct Coordinate
{
    public int x;
    public int y;

    public Coordinate(int x, int y)
    {
        this.x = x;
        this.y = y;
    }
}

Coordinate point = new Coordinate(10, 20);

Console.WriteLine(point.x); //output: 10  
Console.WriteLine(point.y); //output: 20  
```

More info about Struct: https://www.dotnetperls.com/struct

# C# Intermediate Concepts

## Inheritance

A relationship between two classes that allows one to inherit code from the other. Also known as an "Is-A" relationship. Example: A Car is a Vehicle. Allows code re-use and has polymorphic behaviour.

## Composition

A relationship between two classes that allows one to contain the other. Also known as a "Has-a" relationship. Example: Car has an Engine. Allows code re-use, is flexible and it's used to design loose-coupling aplications.

# C# Advanced Concepts

# Fuentes
* https://www.w3schools.com/cs/default.asp
* https://www.tutorialsteacher.com/csharp
