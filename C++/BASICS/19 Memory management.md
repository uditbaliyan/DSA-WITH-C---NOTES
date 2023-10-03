 in C++ involves allocating and deallocating memory for objects and data structures. There are two main approaches to memory management: automatic (stack) and dynamic (heap).

### 1. **Automatic (Stack) Memory Management**

Automatic memory management is handled by the compiler and is associated with the scope of variables. When a variable is declared, memory is automatically allocated for it, and when it goes out of scope, the memory is automatically deallocated.

Example:
```cpp
void myFunction() {
    int x = 10; // Memory for 'x' is allocated on the stack
    // ...
} // 'x' goes out of scope, memory is automatically deallocated
```

Pros:
- Faster allocation and deallocation.
- No need for manual memory management.

Cons:
- Limited in size compared to the heap.
- Objects must have a fixed size known at compile time.

### 2. **Dynamic (Heap) Memory Management**

Dynamic memory management involves allocating memory from the heap (free store) at runtime. This allows you to create objects with a size that may not be known at compile time.

#### **Allocation (new)**

```cpp
int* ptr = new int; // Allocates memory for an integer on the heap
```

#### **Deallocation (delete)**

```cpp
delete ptr; // Deallocates the memory for the integer
```

Example:
```cpp
int* arr = new int[5]; // Allocates an array of 5 integers on the heap
delete[] arr; // Deallocates the memory for the array
```

Pros:
- Allows dynamic allocation of memory.
- Supports objects of variable size.

Cons:
- Slower allocation and deallocation compared to the stack.
- Requires manual deallocation to avoid memory leaks.

### **Memory Leaks**

A memory leak occurs when dynamically allocated memory is not deallocated properly. This can lead to a program consuming more and more memory over time.

Example:
```cpp
void myFunction() {
    int* ptr = new int; // Memory allocated on the heap
    // ... (forgetting to deallocate 'ptr')
}
```

To avoid memory leaks, always remember to deallocate dynamically allocated memory when it is no longer needed.

### **Smart Pointers**

C++ provides smart pointers (`unique_ptr`, `shared_ptr`, `weak_ptr`) which automatically manage the memory of dynamically allocated objects, making it safer and less error-prone compared to manual memory management.

Example (using `unique_ptr`):
```cpp
#include <memory>

std::unique_ptr<int> ptr = std::make_unique<int>(42);
```

Smart pointers automatically deallocate memory when they go out of scope or when they are reset, helping to prevent memory leaks.

Overall, both automatic and dynamic memory management have their own advantages and use cases. It's important to choose the appropriate approach based on the specific requirements of your program.