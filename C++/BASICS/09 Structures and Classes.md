

### Creating and Using Structures

A structure is a user-defined data type that allows you to group together variables of different types.

```cpp
#include <iostream>
using namespace std;

// Define a structure
struct Point {
    int x;
    int y;
};

int main() {
    // Create an instance of the Point structure
    Point p1 = {3, 4};

    cout << "Coordinates: (" << p1.x << ", " << p1.y << ")" << endl;

    return 0;
}
```

In this example, we define a structure `Point` with two integer members (`x` and `y`). We then create an instance of this structure called `p1`.

### Object-Oriented Concepts

Object-oriented programming (OOP) is a programming paradigm that uses objects to organize code. Key concepts include classes, objects, encapsulation, inheritance, polymorphism, and abstraction.

```cpp
#include <iostream>
using namespace std;

// Define a class
class Circle {
private:
    double radius;

public:
    // Constructor
    Circle(double r) : radius(r) {}

    // Getter
    double getRadius() {
        return radius;
    }

    // Setter
    void setRadius(double r) {
        radius = r;
    }

    // Method to calculate area
    double calculateArea() {
        return 3.14 * radius * radius;
    }
};

int main() {
    // Create an instance of the Circle class
    Circle c1(5.0);

    // Use class methods
    cout << "Radius: " << c1.getRadius() << endl;
    cout << "Area: " << c1.calculateArea() << endl;

    return 0;
}
```

In this example, we define a class `Circle` with private member `radius`. We provide a constructor to initialize the radius, getter and setter methods for `radius`, and a method to calculate the area of the circle.

We then create an instance of the `Circle` class called `c1` and use its methods to get the radius and calculate the area.

### Object-Oriented Concepts (Continued)

- **Encapsulation**: Encapsulation is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit or class. In the example above, the `Circle` class encapsulates the `radius` and the methods that operate on it.

- **Inheritance**: Inheritance is a mechanism in which one class can inherit the attributes and behaviors of another class. This allows for code reuse and the creation of hierarchies of classes.

- **Polymorphism**: Polymorphism allows objects to be treated as instances of their base class or as instances of their derived class. It enables multiple forms of the same operation to be performed depending on the context.

- **Abstraction**: Abstraction involves hiding the implementation details of an object and exposing only the relevant features or behavior. This allows for a simpler and more intuitive use of objects.

These are fundamental concepts of object-oriented programming, which allows for better organization, reusability, and scalability of code.



In C++, both structures and classes are used to define custom data types. They share many similarities but have a few key differences. Here's a comparison of structures and classes in C++:

### Similarities:

1. **Member Variables**:
   - Both structures and classes can contain member variables (also known as data members or attributes) to hold data.

   Example:
   ```cpp
   struct Point {
       int x;
       int y;
   };

   class Rectangle {
   public:
       int length;
       int width;
   };
   ```

2. **Member Functions**:
   - Both can have member functions (also known as methods) that operate on the data members.

   Example:
   ```cpp
   struct Point {
       int x;
       int y;
       void print() {
           std::cout << "(" << x << ", " << y << ")" << std::endl;
       }
   };

   class Rectangle {
   public:
       int length;
       int width;
       int area() {
           return length * width;
       }
   };
   ```

3. **Access Specifiers**:
   - Both can use access specifiers (`public`, `protected`, `private`) to control the visibility of members.

   Example:
   ```cpp
   class MyClass {
   public:
       int publicMember;
   private:
       int privateMember;
   };
   ```

### Differences:

1. **Default Access Specifier**:
   - In a `struct`, the default access specifier is `public`, which means that members are accessible by default.
   - In a `class`, the default access specifier is `private`, which means that members are not accessible by default.

   Example:
   ```cpp
   struct Point {
       int x; // Public by default
   };

   class Rectangle {
       int length; // Private by default
   };
   ```

2. **Inheritance**:
   - Classes can be used for inheritance (single, multiple, and hierarchical), allowing one class to inherit the members of another.

   Example:
   ```cpp
   class Parent {
       // ...
   };

   class Child : public Parent {
       // ...
   };
   ```

   Structures do not support inheritance.

3. **Object-Oriented Features**:
   - Classes are primarily used for object-oriented programming (OOP) and support features like polymorphism, encapsulation, and abstraction.

   Example:
   ```cpp
   class Shape {
   public:
       virtual void draw() = 0; // Pure virtual function (abstraction)
   };
   ```

   While you can technically use structures to achieve similar functionality, it's not the typical use case.

### When to Use Which:

- **Use a `struct`**:
   - When you have a small collection of related data with no associated behavior or methods.
   - When you want to group data members together with default public accessibility.

- **Use a `class`**:
   - When you have data along with behavior (methods) that operate on that data.
   - When you're working in an object-oriented paradigm and you want to use features like inheritance and polymorphism.

In practice, many C++ programmers tend to use classes by default, and use structs primarily for cases where compatibility with C or default public accessibility is important.

------------------------
