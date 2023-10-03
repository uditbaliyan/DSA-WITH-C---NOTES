
## Standard Template Library (STL)

### Containers

Containers in the STL are classes or data structures that store and organize data. Some common containers include vectors, lists, maps, and sets.

#### Vectors

Vectors are dynamic arrays that can grow in size.

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {1, 2, 3, 4, 5};

    // Accessing elements
    cout << "First element: " << v[0] << endl;

    // Adding elements
    v.push_back(6);

    // Iterating through elements
    for (int num : v) {
        cout << num << " ";
    }

    return 0;
}
```

#### Lists

Lists are doubly linked lists.

```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    list<int> l = {1, 2, 3, 4, 5};

    // Accessing elements
    cout << "First element: " << l.front() << endl;

    // Adding elements
    l.push_back(6);

    // Iterating through elements
    for (int num : l) {
        cout << num << " ";
    }

    return 0;
}
```

#### Maps

Maps are associative containers that store key-value pairs.

```cpp
#include <iostream>
#include <map>
using namespace std;

int main() {
    map<string, int> ages;

    ages["Alice"] = 30;
    ages["Bob"] = 35;

    // Accessing elements
    cout << "Bob's age: " << ages["Bob"] << endl;

    // Iterating through elements
    for (auto pair : ages) {
        cout << pair.first << " is " << pair.second << " years old." << endl;
    }

    return 0;
}
```

### Algorithms

The STL provides a set of powerful algorithms that operate on containers. Examples include sorting, searching, and manipulating elements.

#### Sorting

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> v = {5, 2, 8, 1, 3};

    // Sorting in ascending order
    sort(v.begin(), v.end());

    // Printing sorted elements
    for (int num : v) {
        cout << num << " ";
    }

    return 0;
}
```

#### Searching

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> v = {5, 2, 8, 1, 3};

    // Searching for an element
    auto it = find(v.begin(), v.end(), 8);

    if (it != v.end()) {
        cout << "Element found at position: " << distance(v.begin(), it) << endl;
    } else {
        cout << "Element not found." << endl;
    }

    return 0;
}
```

### Iterators

Iterators are objects that allow you to traverse through elements in a container.

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v = {1, 2, 3, 4, 5};

    // Using iterators to access elements
    vector<int>::iterator it;

    for (it = v.begin(); it != v.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

These examples demonstrate how to use various containers, algorithms, and iterators in the STL. The STL provides a rich set of tools to efficiently manage and process data in C++.