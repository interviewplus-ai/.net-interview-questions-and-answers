# .NET Interview Questions And Answers

Most targeted up-to-date .NET interview questions and answers list

# Table of Contents

1. [What is the difference between `string` and `StringBuilder` in C#?](#1-what-is-the-difference-between-string-and-stringbuilder-in-c)
2. [How do you handle exceptions in C#?](#2-how-do-you-handle-exceptions-in-c)
3. [What are the access modifiers in C#?](#3-what-are-the-access-modifiers-in-c)
4. [How do you implement inheritance in C#?](#4-how-do-you-implement-inheritance-in-c)
5. [What is the difference between `ref` and `out` parameters in C#?](#5-what-is-the-difference-between-ref-and-out-parameters-in-c)
6. [How do you implement method overloading in C#?](#6-how-do-you-implement-method-overloading-in-c)
7. [What is a delegate in C#?](#7-what-is-a-delegate-in-c)
8. [How do you work with nullable types in C#?](#8-how-do-you-work-with-nullable-types-in-c)
9. [How do you implement an interface in C#?](#9-how-do-you-implement-an-interface-in-c)
10. [What is the difference between `async` and `await` in C#?](#10-what-is-the-difference-between-async-and-await-in-c)
11. [How do you serialize and deserialize objects in C#?](#11-how-do-you-serialize-and-deserialize-objects-in-c)
12. [How do you handle concurrent access in C#?](#12-how-do-you-handle-concurrent-access-in-c)
- [Whats more?](#whats-more)
- [Contributing](#contributing)
- [License](#license)



## 1. What is the difference between string and StringBuilder in C#?

Answer:

```csharp
// Using string
string str = "Hello";
str += " World";

// Using StringBuilder
StringBuilder sb = new StringBuilder();
sb.Append("Hello");
sb.Append(" World");

// The main difference is that string is immutable (it cannot be changed after creation)
// whereas StringBuilder is mutable (it can be modified without creating a new instance)
```

## 2. How do you handle exceptions in C#?

Answer:

```csharp
try
{
    // Code that may throw an exception
}
catch (Exception ex)
{
    // Exception handling code
}
finally
{
    // Code that executes regardless of whether an exception occurred or not
}
```

## 3. What are the access modifiers in C#?

Answer:

```csharp
// Public: Accessible from any code
public class MyClass { }

// Private: Accessible only within the containing class
private int myVariable;

// Protected: Accessible within the containing class and its derived classes
protected void MyMethod() { }

// Internal: Accessible within the same assembly
internal class MyInternalClass { }

// Protected Internal: Accessible within the same assembly or derived classes
protected internal int myField;
```

## 4. How do you implement inheritance in C#?

Answer:

```csharp
// Base class
public class Animal
{
    public string Name { get; set; }

    public void Eat()
    {
        Console.WriteLine("The animal is eating.");
    }
}

// Derived class
public class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("The dog is barking.");
    }
}

// Usage
Dog dog = new Dog();
dog.Name = "Buddy";
dog.Eat();
dog.Bark();
```

## 5. What is the difference between ref and out parameters in C#?

Answer:

```csharp
// ref parameter: Requires the variable to be initialized before passing it to the method
void Increment(ref int number)
{
    number++;
}

int value = 10;
Increment(ref value);
Console.WriteLine(value); // Output: 11

// out parameter: Does not require the variable to be initialized before passing it to the method
bool TryParse(string input, out int number)
{
    return int.TryParse(input, out number);
}

bool success = TryParse("123", out int result);
```

## 6. How do you implement method overloading in C#?

Answer:

```csharp
public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }
}

Calculator calc = new Calculator();
int result1 = calc.Add(5, 10);
double result2 = calc.Add(2.5, 3.7);
```

## 7. What is a delegate in C#?

Answer:

```csharp
// Declaration
delegate void MyDelegate(string message);

// Usage
void DisplayMessage(string message)
{
    Console.WriteLine(message);
}

MyDelegate myDelegate = DisplayMessage;
myDelegate("Hello, delegates!");
```

## 8. How do you work with nullable types in C#?

Answer:

```csharp
int? nullableInt = null;
if (nullableInt.HasValue)
{
    int value = nullableInt.Value;
}
else
{
    // nullableInt is null
}

nullableInt = 42;
int valueOrDefault = nullableInt.GetValueOrDefault(); // 42
```

## 9. How do you implement an interface in C#?

Answer:

```csharp
public interface IShape
{
    double CalculateArea();
}

public class Rectangle : IShape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public double CalculateArea()
    {
        return Width * Height;
    }
}

Rectangle rectangle = new Rectangle();
rectangle.Width = 5;
rectangle.Height = 10;
double area = rectangle.CalculateArea();
```

## 10. What is the difference between async and await in C#?

Answer:

```csharp
// async: Indicates that a method is asynchronous and may use the await keyword
async Task<string> GetDataAsync()
{
    await Task.Delay(1000); // Simulate an asynchronous operation
    return "Data";
}

// await: Pauses the execution of an asynchronous method until the awaited task is complete
async Task ProcessDataAsync()
{
    string data = await GetDataAsync();
    Console.WriteLine(data);
}
```

## 11. How do you serialize and deserialize objects in C#?

Answer:

```csharp
// Serialization: Convert an object to a byte array or a string
MyClass obj = new MyClass();
byte[] bytes = JsonSerializer.SerializeToUtf8Bytes(obj);
string json = JsonSerializer.Serialize(obj);

// Deserialization: Convert a byte array or a string back to an object
MyClass obj1 = JsonSerializer.Deserialize<MyClass>(bytes);
MyClass obj2 = JsonSerializer.Deserialize<MyClass>(json);
```

## 12. How do you handle concurrent access in C#?

Answer:

```csharp
lock (lockObject)
{
    // Critical section where only one thread can execute at a time
}
```

## What's more?
<a href="https://interviewplus.ai/developers-and-programmers/dot-net/questions">A comprehensive list of questions and answers</a>

## Contributing
We welcome contributions from our users to help make this resource as comprehensive and useful as possible. If you have been recently interviewed and encountered a question that is not currently covered on our website, feel free to suggest it as a new question. Your contributions will be added to our platform, and we will make sure to credit you for your contributions. We appreciate your help in making our platform a valuable tool for all job seekers.

## License
MIT License
