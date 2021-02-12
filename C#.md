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

```
using System; 
namespace MyApplication 
{ 
  enum Level 
  { 
    Low, 
    Medium, 
    High 
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
