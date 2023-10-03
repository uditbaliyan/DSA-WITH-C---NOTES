
-------------------------
------------


`extern` is a keyword in C and C++ that is used to declare a global variable or function that is defined in another source file. It's often used when you want to use a variable or function from another source file in your current source file.

Here's how `extern` is typically used:

1. **For Variables**:

   In one source file (e.g., `file1.cpp`), you define the variable:

   ```cpp
   int globalVariable = 10;
   ```

   In another source file (e.g., `file2.cpp`), you declare it using `extern`:

   ```cpp
   extern int globalVariable; // Declaration of globalVariable from file1.cpp
   ```

   Now, `file2.cpp` can use `globalVariable` without having to define it again.

2. **For Functions**:

   Similarly, `extern` is used for function declarations. In one source file, you define the function, and in other files, you declare it.

   For example, in `file1.cpp`:

   ```cpp
   void myFunction() {
       // Implementation of myFunction
   }
   ```

   In `file2.cpp`:

   ```cpp
   extern void myFunction(); // Declaration of myFunction from file1.cpp
   ```

   Now, `file2.cpp` can call `myFunction`.

   It's worth noting that in C++, `extern` is often not required for function declarations. Functions declared in one file are usually accessible in other files by default.

`extern` is particularly useful in large projects where code is spread across multiple files, and you want to share variables or functions between them. It helps in separating declaration from definition.

Additionally, `extern` can be used with global variables to indicate that the variable is declared in another file and should be linked to its definition during the linking phase of compilation.

Example of using `extern` with a global variable:

```cpp
// In file1.cpp
int globalVariable = 10;

// In file2.cpp
extern int globalVariable; // Declaration of globalVariable from file1.cpp

int main() {
    globalVariable = 20; // Accessing and modifying globalVariable
    return 0;
}
```

Remember, if you're working with modern C++, there are usually better ways to handle shared variables or functions, such as using namespaces, classes, or header files with include guards.

