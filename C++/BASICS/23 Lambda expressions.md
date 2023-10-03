, often referred to as lambdas, are a feature introduced in C++11 that allows you to define anonymous functions in-line. They are a concise way to create simple functions without the need for separate function declarations.

Here's the basic syntax of a lambda expression:

```
[ capture-list ] ( parameters ) -> return-type {
    // body of the lambda function
}
```

Let's break down each part:

- **Capture List (`[ ]`)**: Allows you to capture variables from the surrounding scope to use within the lambda. It can be empty or contain variables by value `[var]`, by reference `[&var]`, or by a mix of both `[var, &var2]`.

- **Parameters (`( )`)**: Similar to regular function parameters, lambda expressions can take a list of parameters.

- **Return Type (`-> return-type`)**: Specifies the return type of the lambda function. This part is optional; the return type can often be deduced by the compiler.

- **Lambda Body `{ }`**: Contains the actual code of the lambda function.

### Example 1: Simple Lambda

```cpp
auto sum = [](int a, int b) -> int {
    return a + b;
};

int result = sum(3, 4); // result will be 7
```

### Example 2: Capture List

```cpp
int x = 10;
int y = 5;

auto multiply = [x, &y]() -> int {
    return x * y;
};

int result = multiply(); // result will be 50
```

In this example, `x` is captured by value, meaning it is copied into the lambda, while `y` is captured by reference, allowing the lambda to directly access and modify `y`.

### Example 3: Using Standard Algorithms with Lambda

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> numbers = {3, 1, 4, 1, 5, 9, 2, 6};

    // Using std::for_each with a lambda to print each element
    std::for_each(numbers.begin(), numbers.end(), [](int num) {
        std::cout << num << " ";
    });

    return 0;
}
```

In this example, a lambda is used with `std::for_each` to print each element of the `numbers` vector.

Lambda expressions are particularly useful in scenarios where you need to pass a simple, one-off function as an argument to another function (for example, in algorithms that take a predicate or a comparison function). They provide a concise and readable way to define such functions inline.