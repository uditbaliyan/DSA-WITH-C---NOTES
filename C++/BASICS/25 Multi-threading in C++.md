 allows a program to execute multiple threads concurrently, enabling tasks to be performed in parallel. C++11 and later versions of the language introduced a standardized library for multi-threading, providing classes and functions for managing threads, synchronization, and other related tasks.

Here are some of the key components for multi-threading in C++ using C++11 and above:

### 1. **std::thread**

`std::thread` is a class that represents an individual thread of execution. It allows you to create, join, detach, and manage threads.

Example:
```cpp
#include <iostream>
#include <thread>

void threadFunction() {
    std::cout << "This is a thread!" << std::endl;
}

int main() {
    std::thread myThread(threadFunction); // Create a new thread
    myThread.join(); // Wait for the thread to finish

    return 0;
}
```

### 2. **std::mutex**

`std::mutex` is a class that provides basic mutex functionality for synchronizing access to shared resources. It prevents multiple threads from simultaneously accessing shared data.

Example:
```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;

void threadFunction() {
    mtx.lock(); // Lock the mutex
    std::cout << "This is a thread!" << std::endl;
    mtx.unlock(); // Unlock the mutex
}

int main() {
    std::thread myThread(threadFunction);
    myThread.join();

    return 0;
}
```

### 3. **std::lock_guard**

`std::lock_guard` is a class template that provides a convenient RAII-style mechanism for owning a mutex for the duration of a scoped block.

Example:
```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;

void threadFunction() {
    std::lock_guard<std::mutex> lock(mtx); // Locks the mutex in constructor, unlocks in destructor
    std::cout << "This is a thread!" << std::endl;
}

int main() {
    std::thread myThread(threadFunction);
    myThread.join();

    return 0;
}
```

### 4. **std::condition_variable**

`std::condition_variable` is a synchronization primitive that allows one or more threads to wait until notified by another thread.

Example:
```cpp
#include <iostream>
#include <thread>
#include <mutex>
#include <condition_variable>

std::mutex mtx;
std::condition_variable cv;
bool ready = false;

void threadFunction() {
    std::unique_lock<std::mutex> lock(mtx);
    cv.wait(lock, [](){ return ready; }); // Wait until 'ready' is true
    std::cout << "This is a thread!" << std::endl;
}

int main() {
    std::thread myThread(threadFunction);
    
    // Do some work...
    
    {
        std::lock_guard<std::mutex> lock(mtx);
        ready = true;
    }
    cv.notify_one(); // Notify one waiting thread
    
    myThread.join();

    return 0;
}
```

These are some basic components for multi-threading in C++. It's important to handle synchronization properly to avoid data races and ensure safe concurrent access to shared resources. Additionally, error handling and exception safety are crucial aspects of multi-threaded programming.