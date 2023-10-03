 Exception handling in C++ involves the use of `try`, `catch`, `throw`, and `noexcept`. It allows you to gracefully handle runtime errors.

## Exception Handling

### try, catch, throw

The `try` block is used to enclose the code that may potentially throw an exception. If an exception occurs, it is caught by the `catch` block.

```cpp
#include <iostream>
using namespace std;

int main() {
    try {
        // Code that may throw an exception
        int x = 10;
        int y = 0;

        if (y == 0) {
            throw runtime_error("Division by zero");
        }

        int result = x / y;
        cout << "Result: " << result << endl;
    }
    catch (const runtime_error& e) {
        // Catch block to handle the exception
        cout << "Exception caught: " << e.what() << endl;
    }

    return 0;
}
```

In this example, we attempt to divide `x` by `y`. If `y` is zero, we throw a `runtime_error` with the message "Division by zero". This exception is caught by the `catch` block, and an error message is printed.

### noexcept

The `noexcept` specifier is used to indicate that a function does not throw exceptions.

```cpp
#include <iostream>
using namespace std;

void myFunction() noexcept {
    // Function code
}

int main() {
    try {
        myFunction(); // No exception thrown
    }
    catch (...) {
        cout << "Exception caught." << endl;
    }

    return 0;
}
```

In this example, `myFunction` is marked as `noexcept`, which means it does not throw exceptions. When called within a `try` block, there is no need for a corresponding `catch` block.

### Custom Exceptions

You can create custom exception classes by inheriting from `std::exception` or its subclasses.

```cpp
#include <iostream>
#include <exception>
using namespace std;

class MyException : public exception {
public:
    virtual const char* what() const noexcept {
        return "My custom exception occurred";
    }
};

int main() {
    try {
        throw MyException();
    }
    catch (const exception& e) {
        cout << "Exception caught: " << e.what() << endl;
    }

    return 0;
}
```

In this example, we define a custom exception class `MyException` that inherits from `std::exception`. We override the `what` method to provide a custom error message.

These examples demonstrate how to use `try`, `catch`, `throw`, and `noexcept` for exception handling in C++. This allows you to gracefully handle exceptional situations in your code.