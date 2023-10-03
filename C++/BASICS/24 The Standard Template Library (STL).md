 in C++ provides a rich set of algorithms and functions that operate on containers. These algorithms are implemented as template functions and can be used with various types of containers like vectors, lists, sets, and more.

Here are some commonly used STL algorithms and functions:

### 1. **for_each**

```cpp
#include <algorithm>
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // Apply a function to each element in the range
    std::for_each(numbers.begin(), numbers.end(), [](int num) {
        std::cout << num << " ";
    });

    return 0;
}
```

### 2. **find**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    
    auto it = std::find(numbers.begin(), numbers.end(), 3);

    if (it != numbers.end()) {
        // Element found
    } else {
        // Element not found
    }

    return 0;
}
```

### 3. **sort**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {5, 2, 8, 1, 3};

    std::sort(numbers.begin(), numbers.end()); // Sort in ascending order

    return 0;
}
```

### 4. **reverse**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    std::reverse(numbers.begin(), numbers.end()); // Reverse the order of elements

    return 0;
}
```

### 5. **accumulate**

```cpp
#include <numeric>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    int sum = std::accumulate(numbers.begin(), numbers.end(), 0); // Calculate the sum

    return 0;
}
```

### 6. **count**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 2, 3, 2, 4};

    int numTwos = std::count(numbers.begin(), numbers.end(), 2); // Count occurrences of 2

    return 0;
}
```

### 7. **find_if**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    auto it = std::find_if(numbers.begin(), numbers.end(), [](int num) {
        return num % 2 == 0; // Find the first even number
    });

    return 0;
}
```

### 8. **max_element / min_element**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {3, 1, 4, 1, 5, 9, 2, 6};

    auto max = std::max_element(numbers.begin(), numbers.end()); // Find the maximum element
    auto min = std::min_element(numbers.begin(), numbers.end()); // Find the minimum element

    return 0;
}
```

### 9. **remove / remove_if**

```cpp
#include <algorithm>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 2, 3, 2, 4};

    numbers.erase(std::remove(numbers.begin(), numbers.end(), 2), numbers.end()); // Remove all occurrences of 2

    return 0;
}
```

### 10. **transform**

```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::vector<int> squared;

    std::transform(numbers.begin(), numbers.end(), std::back_inserter(squared), [](int num) {
        return num * num; // Square each element
    });

    return 0;
}
```

These are just a few examples of the many powerful algorithms and functions provided by the STL. They can save you a lot of time and effort when working with containers in C++.