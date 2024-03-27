# c#

# program 1::

```
using System;
public class Arthematic
{
public static void Main(string [] args)
{
System.Console.WriteLine("Enter a First Number: ");
int num1 = Convert.ToInt32(Console.ReadLine());
System.Console.WriteLine("Enter a Second Number: ");
int num2 = Convert.ToInt32(Console.ReadLine());
System.Console.WriteLine("{0} + {1} = {2}", num1, num2, num1 + num2);
System.Console.WriteLine("{0} - {1} = {2}", num1, num2, num1 - num2);
System.Console.WriteLine("{0} x {1} = {2}", num1, num2, num1 * num2);
System.Console.WriteLine("{0} / {1} = {2}", num1, num2, num1 / num2);
System.Console.WriteLine("{0} mod {1} = {2}", num1, num2, num1 % num2);
}
}

```

ouput ::
Enter a First Number: 
1
Enter a Second Number: 
2
1 + 2 = 3
1 - 2 = -1
1 x 2 = 2
1 / 2 = 0
1 mod 2 = 1

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# program 2 ::

```
using System;
public class Armstrong
{
public static void Main(string[] args)
{
int a, b, c, d;
for (int i = 1; i <= 1000; i++)
{
a = i / 100;
b = (i - a * 100) / 10;
c = (i - a * 100 - b * 10);
d = a * a * a + b * b * b + c * c * c;
if (i == d)
{
System.Console.WriteLine("{0}", i);
}
}
}
}
```

output::
1
153
370
371
407
1000

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 3::

```
using System;
public class Substrings
{
public static void find_substrings(string input_string)
{
int j = 0;
int i = 0;
for (i = 1; i <= input_string.Length; i++)
{
for (j = 0; j <= input_string.Length - i; j++)
{
System.Console.WriteLine(input_string.Substring(j, i));
}
}
}
public static void Main(string [] args)
{
string input_string;
System.Console.WriteLine("Enter a String :");
input_string = System.Console.ReadLine();
find_substrings(input_string);
}
}
```

output ::
Enter a String :
hello
e
l
l
o
el
ll
lo
ell
llo
ello

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 4::

```
using System;

class Program
{
    static void Main()
    {
        DivisionByZeroExceptionExample();
        IndexOutOfRangeExceptionExample();
    }
    

    static void DivisionByZeroExceptionExample()
    {
        try
        {
            Console.Write("Enter numerator: ");
            int numerator = int.Parse(Console.ReadLine());
            Console.Write("Enter denominator: ");
            int denominator = int.Parse(Console.ReadLine());
            int result = numerator / denominator;
            Console.WriteLine("Result of division: " + result);
        }
        catch (Exception ex) when (ex is DivideByZeroException || ex is FormatException)
        {
            Console.WriteLine(ex is DivideByZeroException ? "Division by Zero Exception: " + ex.Message : "Invalid input. Please enter valid integers for numerator and denominator.");
        }
    }

    static void IndexOutOfRangeExceptionExample()
    {
        try
        {
            Console.Write("Enter index to access in array: ");
            int index = int.Parse(Console.ReadLine());
            int[] numbers = { 1, 2, 3, 4, 5 };
            int value = numbers[index];
            Console.WriteLine("Value at index: " + value);
        }
        catch (Exception ex) when (ex is IndexOutOfRangeException || ex is FormatException)
        {
            Console.WriteLine(ex is IndexOutOfRangeException ? "Index Out of Range Exception: " + ex.Message : "Invalid input. Please enter a valid integer for the array index.");
        }
    }
}

```
output ::

Enter numerator: 10
Enter denominator: 2
Result of division: 5
Enter index to access in array: 4
Value at index: 5

Enter numerator: 10
Enter denominator: 0
Division by Zero Exception: Attempted to divide by zero.
Enter index to access in array: 5
Index Out of Range Exception: Index was outside the bounds of the array.

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 5::

```
using System;

class Program
{
    static void Main(string[] args)
    {
        int rows = 5; // Number of rows in Pascal's triangle

        for (int i = 0; i < rows; i++)
        {
            int number = 1;
            Console.Write(new string(' ', (rows - i) * 2));
            for (int j = 0; j <= i; j++)
            {
                Console.Write("{0,3} ", number);
                number = number * (i - j) / (j + 1);
            }
            Console.WriteLine();
        }
    }
}

```
output ::
Enter the number of rows for Pascal's Triangle: 5
Pascal's Triangle:
 ``
            1 
          1   1 
        1   2   1 
      1   3   3   1 
    1   4   6   4   1 
``

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# program 6::

```
using System;

class Program
{
    static void Main(string[] args)
    {
        int rows = 5; // Number of rows in Floyd's triangle
        int number = 1;

        for (int i = 1; i <= rows; i++)
        {
            for (int j = 1; j <= i; j++)
            {
                Console.Write(number + " ");
                number++;
            }
            Console.WriteLine();
        }
    }
}

```
output::
Enter the number of rows: 5
``
1 
2 3 
4 5 6 
7 8 9 10 
11 12 13 14 15 
``
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# program 7::
```
using System;
using System.IO;
class Program
{
    static void Main()
    {
        try
        {
            Console.Write("Enter the source file path: ");
            string sourceFilePath = Console.ReadLine();
            Console.Write("Enter the destination file path: ");
            string destinationFilePath = Console.ReadLine();
            string fileContents = ReadFile(sourceFilePath);
            WriteFile(destinationFilePath, fileContents);
            Console.WriteLine("File contents copied successfully.");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"An error occurred: {ex.Message}");
        }
    }
    static string ReadFile(string filePath)
    {
        using (StreamReader reader = new StreamReader(filePath))
        {
            return reader.ReadToEnd();
        }
    }
    static void WriteFile(string filePath, string content)
    {
        using (StreamWriter writer = new StreamWriter(filePath))
        {
            writer.Write(content);
        }
    }
}
```
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
# program 8::
```
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace ConsoleApplication
{
public class Stack
{
public static void Main(string [] args)
{
stack st = new stack();
while (true)
{
System.Console.Clear();
System.Console.WriteLine("\nStack MENU(size -- 10)");
System.Console.WriteLine("1. Add an element");
System.Console.WriteLine("2. See the Top element.");
System.Console.WriteLine("3. Remove top element.");
System.Console.WriteLine("4. Display stack elements.");
System.Console.WriteLine("5. Exit");
System.Console.Write("Select your choice: ");
int choice = Convert.ToInt32(System.Console.ReadLine());
switch (choice)
{
case 1:
System.Console.WriteLine("Enter an Element : ");
st.Push(Console.ReadLine());
break;
case 2:
System.Console.WriteLine("Top element is: {0}", st.Peek());
break;
case 3:
System.Console.WriteLine("Element removed: {0}", st.Pop());
break;
case 4:
st.Display();
break;
case 5:
System.Environment.Exit(1);
break;
}
System.Console.ReadKey();
}
}
}
public interface StackADT
{
public Boolean isEmpty();
public void Push(Object element);
public Object Pop();
public Object Peek();
public void Display();
}
public class stack : StackADT
{
private int StackSize;
public int StackSizeSet
{
get { return StackSize; }
set { StackSize = value; }
}
public int top;
public Object[] item;
public stack()
{
StackSizeSet = 10;
item = new Object[StackSizeSet];
top = -1;
}
public stack(int capacity)
{
StackSizeSet = capacity;
item = new Object[StackSizeSet];
top = -1;
}
public bool isEmpty()
{
if (top == -1) return true;
return false;
}
public void Push(object element)
{
if (top == (StackSize - 1))
{
System.Console.WriteLine("Stack is full!");
}
else
{
item[++top] = element;
System.Console.WriteLine("Item pushed successfully!");
}
}
public object Pop()
{
if (isEmpty())
{
System.Console.WriteLine("Stack is empty!");
return "No elements";
}
else
{
return item[top--];
}
}
public object Peek()
{
if (isEmpty())
{
System.Console.WriteLine("Stack is empty!");
return "No elements";
}
else
{
return item[top];
}
}
public void Display()
{
for (int i = top; i > -1; i--)
{
System.Console.WriteLine("Item {0}: {1}", (i + 1), item[i]);
}
}
}
}
```
output ::
Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 1
Enter an Element :
2 4 5 3
Item pushed successfully!***********************************************Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 2
Top element is: 2 4 5 3***********************************************Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 4
Item 1: 2 4 5 3***********************************************Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 3
Element removed: 2 4 5 3***********************************************Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 2
Stack is empty!
Top element is: No elements***********************************************Stack MENU(size -- 10)
1. Add an element
2. See the Top element.
3. Remove top element.
4. Display stack elements.
5. Exit
Select your choice: 5

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 9::
```
using System;
public struct Complex
{
public int real;
public int imaginary;
public Complex(int real, int imaginary)
{
this.real = real;
this.imaginary = imaginary;
}
public static Complex operator +(Complex one, Complex two)
{
return new Complex(one.real + two.real, one.imaginary + two.imaginary);
}
public override string ToString()
{
return (String.Format("{0} + {1}i", real, imaginary));
}
}
public class VtuCode
{
public static void Main(string [] args)
{
Complex val1 = new Complex(7, 1);
Complex val2 = new Complex(2, 6);
Complex res = val1 + val2;
System.Console.WriteLine("First: {0}", val1);
System.Console.WriteLine("Second: {0}", val2);
System.Console.WriteLine("Result (Sum): {0}", res);
System.Console.ReadLine();
}
}
```
////////////////////////////////////////////////////////////////////////////////////////

# program 9::
```
using System;
public struct Complex
{
public int real;
public int imaginary;
public Complex(int real, int imaginary)
{
this.real = real;
this.imaginary = imaginary;
}
public static Complex operator +(Complex one, Complex two)
{
return new Complex(one.real + two.real, one.imaginary + two.imaginary);
}
public override string ToString()
{
return (String.Format("{0} + {1}i", real, imaginary));
}
}
public class VtuCode
{
public static void Main(string [] args)
{
Complex val1 = new Complex(1, 4);
Complex val2 = new Complex(2, 1);
Complex res = val1 + val2;
System.Console.WriteLine("First: {0}", val1);
System.Console.WriteLine("Second: {0}", val2);
System.Console.WriteLine("Result (Sum): {0}", res);
System.Console.ReadLine();
}
}
```
output::
First: 1 + 4i
Second: 2 + 1i
Result (Sum): 3 + 5i

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 10:;
```
using System;
public class Shape
{
public virtual void draw()
{
Console.WriteLine("Drawing Shape");
}
public virtual void erase()
{
Console.WriteLine("Erasing Shape");
}
}
public class Circle : Shape
{
public override void draw()
{
Console.WriteLine("Drawing Circle");
}
public override void erase()
{
Console.WriteLine("Erasing Circle");
}
}
public class Triangle : Shape
{
public override void draw()
{
Console.WriteLine("Drawing Triangle");
}
public override void erase()
{
Console.WriteLine("Erasing Triangle");
}
}
public class Square : Shape
{
public override void draw()
{
Console.WriteLine("Drawing Square");
}
public override void erase()
{
Console.WriteLine("Erasing Square");
}
}
public class Program
{
public static void Main()
{
Shape[] shapes = new Shape[3];
shapes[0] = new Circle();
shapes[1] = new Triangle();
shapes[2] = new Square();
foreach (Shape shape in shapes)
{
shape.draw(); shape.erase();
}
}
}
```

output::
Drawing Circle
Erasing Circle
Drawing Triangle
Erasing Triangle
Drawing Square
Erasing Square


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 11:;
```
using System;

public abstract class Shape
{
    public abstract double GetPerimeter();
    public abstract double GetArea();
}

public class Circle : Shape
{
    private const double PI = Math.PI;
    private double radius;

    public Circle(double radius = 1) => this.radius = radius;

    public override double GetArea() => PI * radius * radius;
    public override double GetPerimeter() => 2 * PI * radius;
}

public class Triangle : Shape
{
    private double width, height;

    public Triangle(double width = 1, double height = 1) => (this.width, this.height) = (width, height);

    public override double GetArea() => width * height / 2;
    public override double GetPerimeter() => width + height + Math.Sqrt(width * width + height * height);
}

public class ShapeClient
{
    public static void Main(string[] args)
    {
        Shape triangle = new Triangle(10, 11);                                                                                                     change values in this line
        Console.WriteLine("Triangle:");
        Console.WriteLine($"Area: {triangle.GetArea()}\nPerimeter: {triangle.GetPerimeter()}");

        Shape circle = new Circle(6);                                                                                                                     change values in this line
        Console.WriteLine("\nCircle:");
        Console.WriteLine($"Area: {circle.GetArea()}\nPerimeter: {circle.GetPerimeter()}");
    }
}

```
output  ::
Triangle:
Area: 55
Perimeter: 35.8660687473185

Circle:
Area: 113.097335529233
Perimeter: 37.6991118430775


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


# program 12::
```
using System;
// Resizable Interface
public interface IResizable
{
    void ResizeWidth(int width);
    void ResizeHeight(int height);
}
// Rectangle Class implementing the Resizable interface
public class Rectangle : IResizable
{
    private int width;
    private int height;
    // Constructor
    public Rectangle(int initialWidth, int initialHeight)
    {
        width = initialWidth;
        height = initialHeight;
    }
    // Implementing methods from the Resizable interface
    public void ResizeWidth(int newWidth)
    {
        width = newWidth;
        Console.WriteLine($"Width resized to: {width}");
    }
    public void ResizeHeight(int newHeight)
    {
        height = newHeight;
        Console.WriteLine($"Height resized to: {height}");
    }

    // Additional method to display rectangle information
    public void DisplayRectangleInfo()
    {
        Console.WriteLine($"Rectangle Width: {width}, Height: {height}");
    }
}
class Program
{
    static void Main(string[] args)
    {
        // Creating a Rectangle object
        Rectangle myRectangle = new Rectangle(5, 10);
        // Displaying initial rectangle information
        Console.WriteLine("Initial Rectangle:");
        myRectangle.DisplayRectangleInfo();
        // Resizing width and height
        myRectangle.ResizeWidth(8);
        myRectangle.ResizeHeight(15);  
        // Displaying updated rectangle information 
        Console.WriteLine("\nUpdated Rectangle:");
        myRectangle.DisplayRectangleInfo(); 
        Console.ReadLine(); // To keep the console window open
    }
}

  
```
output::

Initial Rectangle:
Rectangle Width: 5
Height: 10
//////////////////////////
Width resized to: 8
Height resized to: 15
//////////////////////////
Updated Rectangle:
Rectangle Width: 8, Height: 15




