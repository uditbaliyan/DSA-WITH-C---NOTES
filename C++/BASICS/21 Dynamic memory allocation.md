 in C++ allows you to allocate memory at runtime, rather than at compile time. This means you can create data structures with a size that is determined during program execution. Dynamic memory allocation is performed using pointers.

Here are the key operators and functions used for dynamic memory allocation in C++:

### 1. **`new` Operator**

The `new` operator is used to dynamically allocate memory on the heap.

Example:
```cpp
int* ptr = new int; // Allocates memory for an integer on the heap
```

### 2. **`delete` Operator**

The `delete` operator is used to deallocate memory that was previously allocated using `new`.

Example:
```cpp
delete ptr; // Deallocates the memory for the integer
```

### 3. **`new[]` Operator (For Arrays)**

The `new[]` operator is used to dynamically allocate memory for an array on the heap.

Example:
```cpp
int* arr = new int[5]; // Allocates an array of 5 integers on the heap
```

### 4. **`delete[]` Operator (For Arrays)**

The `delete[]` operator is used to deallocate memory for an array that was previously allocated using `new[]`.

Example:
```cpp
delete[] arr; // Deallocates the memory for the array
```

### 5. **`malloc()` Function**

The `malloc()` function allocates a block of memory on the heap and returns a pointer to the beginning of that block.

Example:
```cpp
int* ptr = (int*)malloc(sizeof(int)); // Allocates memory for an integer on the heap
```

### 6. **`free()` Function**

The `free()` function is used to deallocate memory that was previously allocated using `malloc()`.

Example:
```cpp
free(ptr); // Deallocates the memory for the integer
```

### 7. **`realloc()` Function**

The `realloc()` function is used to change the size of a previously allocated block of memory.

Example:
```cpp
int* newPtr = (int*)realloc(ptr, sizeof(int) * 2); // Resizes the block of memory to hold 2 integers
```

It's important to note that when using `malloc()`, `realloc()`, and `free()`, you need to explicitly cast the returned pointer to the appropriate type.

### Example: Dynamic Memory Allocation and Deallocation

```cpp
int* ptr = new int; // Allocate memory for an integer
*ptr = 42; // Assign a value to the allocated memory

delete ptr; // Deallocate the memory

int* arr = new int[5]; // Allocate an array of 5 integers

delete[] arr; // Deallocate the array
```

Dynamic memory allocation is useful when you need to create data structures whose size is not known at compile time or when you want to manage memory manually for specific reasons. However, it's important to be cautious and ensure that you deallocate the memory properly to avoid memory leaks.