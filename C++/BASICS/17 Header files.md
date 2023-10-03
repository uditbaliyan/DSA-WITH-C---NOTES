 in C++ are files that contain declarations of functions, classes, variables, and other constructs that can be used in a program. They typically have a `.h` or `.hpp` extension.

Here's how header files work:

1. **Declaration of Functions and Classes**: A header file contains the declarations (signatures) of functions, classes, and other constructs. These declarations tell the compiler that the functions or classes exist, but don't provide their implementations.

    Example (in `my_header.h`):
    ```cpp
    // Function declaration
    int add(int a, int b);

    // Class declaration
    class MyClass {
        // ...
    };
    ```

2. **Inclusion in Source Files**: In your source files (`.cpp` files), you include the header files using the `#include` directive. This effectively "pastes" the content of the header file into your source file.

    Example (in `main.cpp`):
    ```cpp
    #include "my_header.h"

    int main() {
        int result = add(3, 4);
        // ...
        return 0;
    }
    ```

3. **Compilation**: When you compile your program, the compiler first processes the source files. It reads the `#include` directives and includes the contents of the referenced header files.

4. **Linking**: The compiled code from your source files is then linked together with any external libraries to create the final executable.

Header files are used to promote modularity and reusability in your code. By separating the declarations from the implementations, you can include the same header file in multiple source files, allowing you to use the same functions or classes in different parts of your program.

It's important to note that header files should only contain declarations, not definitions. Definitions (actual code) should be in corresponding source files (`.cpp` files).

If you have a class, it's common to have two files: a header file with the class declaration and a source file with the class implementation. This separation allows you to hide the implementation details and only provide a public interface to users of the class.