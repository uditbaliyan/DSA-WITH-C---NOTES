 in C++ are commands that are processed before the actual compilation of the code begins. They are indicated by the `#` symbol at the beginning of a line. Preprocessor directives do not end with a semicolon.

Here are some commonly used preprocessor directives:

### 1. `#include`

The `#include` directive is used to include the contents of a file in your program. It's typically used to include header files containing declarations of functions, classes, and variables.

Example:
```cpp
#include <iostream>
```

### 2. `#define`

The `#define` directive is used to create macros. A macro is a piece of code in your program which has been given a name. When the name is used, it is replaced by the code it represents.

Example:
```cpp
#define MAX_SIZE 100
```

### 3. `#ifdef`, `#ifndef`, `#endif`, and `#else`

These directives are used for conditional compilation. They allow you to include or exclude sections of code based on whether a certain condition is true or false.

Example:
```cpp
#ifdef DEBUG
    // Debugging code here
#else
    // Release code here
#endif
```

### 4. `#pragma`

The `#pragma` directive provides a way to give special instructions to the compiler. It is often used to control compiler-specific behavior.

Example:
```cpp
#pragma once
```

### 5. `#error` and `#warning`

These directives allow you to generate error or warning messages during compilation.

Example:
```cpp
#ifdef OLD_VERSION
    #error "You are using an outdated version!"
#endif
```

### 6. `#undef`

The `#undef` directive is used to undefine a previously defined macro.

Example:
```cpp
#define MAX_SIZE 100
#undef MAX_SIZE
```

These preprocessor directives provide a way to manipulate and conditionally include/exclude portions of code before it is actually compiled. They offer a degree of flexibility and control over the compilation process.