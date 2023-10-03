 is a collection of classes, functions, macros, and templates that provides a comprehensive set of tools for common programming tasks. It is part of the C++ Standard and is available to all C++ programs.

Here's an overview of some key components of the C++ Standard Library:

### 1. **iostream**

The `iostream` library provides facilities for performing input and output operations. It includes `cin` (for input), `cout` (for output), and `cerr` (for error output), among others.

Example:
```cpp
#include <iostream>

int main() {
    int num;
    std::cout << "Enter a number: ";
    std::cin >> num;
    std::cout << "You entered: " << num << std::endl;
    return 0;
}
```

### 2. **vector**

The `vector` is a dynamic array that can grow and shrink in size. It provides efficient random access to elements and supports dynamic resizing.

Example:
```cpp
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    numbers.push_back(6); // Add an element to the end
    int thirdElement = numbers[2]; // Access the third element

    return 0;
}
```

### 3. **string**

The `string` class provides a convenient and efficient way to work with strings of characters. It includes a wide range of member functions for string manipulation.

Example:
```cpp
#include <string>

int main() {
    std::string greeting = "Hello, World!";
    int length = greeting.length(); // Get the length of the string

    return 0;
}
```

### 4. **algorithm**

The `algorithm` library provides a collection of functions for common operations on sequences, such as sorting, searching, and manipulating elements.

Example (using `std::sort`):
```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {5, 2, 8, 1, 3};
    std::sort(numbers.begin(), numbers.end()); // Sort in ascending order

    return 0;
}
```

### 5. **map**

The `map` is an associative container that stores elements in a key-value pair. It allows for efficient retrieval of values based on their associated keys.

Example:
```cpp
#include <map>

int main() {
    std::map<std::string, int> ages;
    ages["Alice"] = 30;
    ages["Bob"] = 35;
    int bobsAge = ages["Bob"]; // Retrieve Bob's age

    return 0;
}
```

### 6. **set**

The `set` is an associative container that stores unique elements in a sorted order. It does not allow duplicates.

Example:
```cpp
#include <set>

int main() {
    std::set<int> numbers = {5, 2, 8, 1, 3, 5, 2};
    // After this, numbers will contain {1, 2, 3, 5, 8}

    return 0;
}
```

### 7. **iterator**

The `iterator` library provides a framework for iterators, which are objects that allow you to traverse sequences of elements.

Example:
```cpp
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    for (auto it = numbers.begin(); it != numbers.end(); ++it) {
        int num = *it; // Access element through iterator
    }

    return 0;
}
```

These are just a few examples of the many components available in the C++ Standard Library. It provides a powerful set of tools for a wide range of programming tasks, allowing you to write efficient and maintainable code.


In C++, the `<cmath>` header provides a library of mathematical functions that can be used for various calculations. Here are some commonly used functions from the `<cmath>` library:

1. **Trigonometric Functions**:

   - `sin(x)`: Returns the sine of `x` (in radians).
   - `cos(x)`: Returns the cosine of `x` (in radians).
   - `tan(x)`: Returns the tangent of `x` (in radians).
   - `asin(x)`: Returns the arcsine of `x` (in radians).
   - `acos(x)`: Returns the arccosine of `x` (in radians).
   - `atan(x)`: Returns the arctangent of `x` (in radians).
   - `atan2(y, x)`: Returns the arctangent of `y/x` (in radians), using the signs of both `y` and `x` to determine the quadrant of the result.

2. **Exponential and Logarithmic Functions**:

   - `exp(x)`: Returns the exponential value of `x`.
   - `log(x)`: Returns the natural logarithm (base e) of `x`.
   - `log10(x)`: Returns the base-10 logarithm of `x`.
   - `pow(x, y)`: Returns `x` raised to the power `y`.
   - `sqrt(x)`: Returns the square root of `x`.

3. **Rounding and Remainder Functions**:

   - `ceil(x)`: Returns the smallest integer greater than or equal to `x`.
   - `floor(x)`: Returns the largest integer less than or equal to `x`.
   - `round(x)`: Rounds `x` to the nearest integer value.
   - `trunc(x)`: Truncates `x` to an integer.

4. **Absolute Value Functions**:

   - `abs(x)`: Returns the absolute value of `x`.
   - `fabs(x)`: Returns the absolute value of `x` (for floating-point values).

5. **Power and Exponential Functions**:

   - `pow(x, y)`: Returns `x` raised to the power `y`.
   - `exp(x)`: Returns the exponential value of `x`.

6. **Hyperbolic Functions**:

   - `sinh(x)`: Returns the hyperbolic sine of `x`.
   - `cosh(x)`: Returns the hyperbolic cosine of `x`.
   - `tanh(x)`: Returns the hyperbolic tangent of `x`.

7. **Constants**:

   - `M_PI`: Represents the mathematical constant π (pi).
   - `M_E`: Represents the mathematical constant e.

Example of using some of these functions:

```cpp
#include <iostream>
#include <cmath>

int main() {
    double x = 3.14;
    double y = -2.71;
    
    double sine_x = sin(x);
    double log_y = log(fabs(y));  // Using fabs to ensure positive value for log
    double sqrt_x = sqrt(x);

    std::cout << "sin(" << x << ") = " << sine_x << std::endl;
    std::cout << "log(|" << y << "|) = " << log_y << std::endl;
    std::cout << "sqrt(" << x << ") = " << sqrt_x << std::endl;

    return 0;
}
```

Remember to include the `<cmath>` header at the beginning of your code to use these functions.