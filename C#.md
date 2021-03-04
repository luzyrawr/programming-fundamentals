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

We have a class *PresentationObject*

```
using System;

namespace Inheritance
{
    public class PresentationObject
    {
        public int Width { get; set; }
        public int Height { get; set; }

        public void Copy()
        {
            Console.WriteLine("Object copied to clipboard.");
        }

        public void Duplicate()
        {
            Console.WriteLine("Object was duplicated.");
        }
    }
}
```

And we have a class *Text* that is a *PresentationObject*

```
using System;

namespace Inheritance
{
    public class Text : PresentationObject
    {
        public int FontSize { get; set; }
        public string FontName { get; set; }

        public void AddHyperlink(string url)
        {
            Console.WriteLine("We added a link to " + url);
        }

    }
}
```

## Composition

A relationship between two classes that allows one to contain the other. Also known as a "Has-a" relationship. Example: Car has an Engine. Allows code re-use, is flexible and it's used to design loose-coupling aplications.

We have a class *Logger*

```
using System;

namespace Composition
{
    public class Logger
    {
        public void Log(string message)
        {
            Console.WriteLine(message);
        }
    }
}
```

We have a class *DbMigrator* that has a *Logger*

```
namespace Composition
{
    public class DbMigrator
    {
        private readonly Logger _logger;

        public DbMigrator(Logger logger)
        {
            _logger = logger;
        }

        public void Migrate()
        {
            _logger.Log("We are migrating blah blah blah...");
        }
    }
}
```

## Upcasting and Downcasting

Convertions between Base Class and Derived Class

```
public class Shape
{
}

public class Circle : Shape
{
}
```

Upcasting is used to convert a derived class to it's base class.

```
Circle circle = new Circle();
Shape shape = circle;
```

Downcasting is used to convert a base class to a derived class.

```
Circle circle = new Circle();
Shape shape = circle;

//Using a explicit convertion
Circle otherCircle = (Circle)shape;

//Using the as keyword
Circle otherCircle = shape as Circle;
if(otherCircle != null)
{
  ...
}

//Using the is keyword
if(otherCircle is Circle)
{
  Circle otherCircle = (Circle)shape;
  ...
}
```

# C# Advanced Concepts

## Attributes
An attribute is a declarative tag that is used to convey information to runtime about the behaviors of various elements like classes, methods, structures, enumerators, assemblies etc. in your program. **You can add declarative information to a program by using an attribute**. A declarative tag is depicted by square ([ ]) brackets placed above the element it is used for.

Attributes are used for adding metadata, such as compiler instruction and other information such as comments, description, methods and classes to a program. The .Net Framework provides two types of attributes: the pre-defined attributes and custom built attributes.

```
[Serializable]
public class SampleClass
{
    // Objects of this type can be serialized.
}

public void MethodA([In][Out] ref double x) 
{ 
    // Parameters to methods can have attributes
}
```

## Reflection
Reflection objects are used for obtaining **type** information at runtime. The classes that give access to the metadata of a running program are in the System.Reflection namespace. The System.Reflection namespace contains classes that allow you to obtain information about the application and to dynamically add types, values, and objects to the application.

Reflection has the following applications −

* It allows view attribute information at runtime.
* It allows examining various types in an assembly and instantiate these types.
* It allows late binding to methods and properties.
* It allows creating new types at runtime and then performs some tasks using those types.

```
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type); //The output is: System.Int32.
```

## Generics
In C#, generic means not specific to a particular data type.

C# allows you to define generic classes, interfaces, abstract classes, fields, methods, static methods, properties, events, delegates, and operators using the type parameter and without the specific data type. A type parameter is a placeholder for a particular type specified when creating an instance of the generic type.

A generic type is declared by specifying a type parameter in an angle brackets after a type name, e.g. *TypeName<T>* where *T* is a type parameter.

```
class DataStore<T>
{
    public T Data { get; set; }
}

DataStore<string> strStore = new DataStore<string>();
strStore.Data = "Hello World!";
//strStore.Data = 123; // compile-time error

DataStore<int> intStore = new DataStore<int>();
intStore.Data = 100;
//intStore.Data = "Hello World!"; // compile-time error
```

### Generic Constraints
C# allows you to use constraints to restrict client code to specify certain types while instantiating generic types. It will give a compile-time error if you try to instantiate a generic type using a type that is not allowed by the specified constraints.

You can specify one or more constraints on the generic type using the where clause after the generic type name.

```
GenericTypeName<T> where T  : contraint1, constraint2

class DataStore<T> where T : class
{
    public T Data { get; set; }
}

DataStore<string> store = new DataStore<string>(); // valid
DataStore<MyClass> store = new DataStore<MyClass>(); // valid
DataStore<IMyInterface> store = new DataStore<IMyInterface>(); // valid
DataStore<IEnumerable> store = new DataStore<IMyInterface>(); // valid
DataStore<ArrayList> store = new DataStore<ArrayList>(); // valid
//DataStore<int> store = new DataStore<int>(); // compile-time error 
```

### Generic Collections
Generic Collections
C# includes the following generic collection classes in the System.Collections.Generic namespace.

| Generic Collections | Description |
| ------------- | ------------- |
| List<T>	| Generic List<T> contains elements of specified type. It grows automatically as you add elements in it. |
| Dictionary<TKey,TValue>	 | Dictionary<TKey,TValue> contains key-value pairs. |
| SortedList<TKey,TValue>	| SortedList stores key and value pairs. It automatically adds the elements in ascending order of key by default. |
| Queue<T>	| Queue<T> stores the values in FIFO style (First In First Out). It keeps the order in which the values were added. It provides an Enqueue() method to add values and a Dequeue() method to retrieve values from the collection. |
| Stack<T> | Stack<T> stores the values as LIFO (Last In First Out). It provides a Push() method to add a value and Pop() & Peek() methods to retrieve values. |
| Hashset<T> | Hashset<T> contains non-duplicate elements. It eliminates duplicate elements. |

# Fuentes
* https://www.w3schools.com/cs/default.asp
* https://www.tutorialsteacher.com/csharp
* https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/
* https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/reflection
