

Templates in C++ allow you to write generic code that can work with any data type. This provides a powerful tool for code reusability.

### Function Templates

A function template allows you to write a generic function that can work with different data types.

```cpp
#include <iostream>
using namespace std;

template <typename T>
T max(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    int intMax = max(3, 5);
    double doubleMax = max(3.5, 2.8);

    cout << "Max of 3 and 5: " << intMax << endl;
    cout << "Max of 3.5 and 2.8: " << doubleMax << endl;

    return 0;
}
```

In this example, we define a function template `max` that takes two parameters of type `T` and returns the larger of the two. The template parameter `T` represents a placeholder for any data type. When the function is called, the appropriate data type is inferred.

### Class Templates

A class template allows you to create a generic class that can work with different data types.

```cpp
#include <iostream>
using namespace std;

template <typename T>
class Pair {
private:
    T first;
    T second;

public:
    Pair(T a, T b) : first(a), second(b) {}

    T getFirst() {
        return first;
    }

    T getSecond() {
        return second;
    }
};

int main() {
    Pair<int> intPair(3, 5);
    Pair<double> doublePair(2.5, 4.8);

    cout << "First value of intPair: " << intPair.getFirst() << endl;
    cout << "Second value of doublePair: " << doublePair.getSecond() << endl;

    return 0;
}
```

In this example, we define a class template `Pair` with two generic members (`first` and `second`). The template parameter `T` is used to represent any data type. When creating instances of `Pair`, you specify the data type within angle brackets (`Pair<int>` and `Pair<double>` in this case).

These are examples of function and class templates, which provide a powerful mechanism for writing generic code that can be used with various data types. They contribute to code flexibility and reusability in C++.