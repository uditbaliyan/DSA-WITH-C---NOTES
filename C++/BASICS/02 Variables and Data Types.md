


## Variables and Data Types

### Integer Types

Integer types represent whole numbers. They can be classified based on their size and signedness (whether they can represent negative numbers).

#### Common Integer Types:

1. **int**: This is the most commonly used integer type. It typically represents a 32-bit signed integer.

2. **short**: Also known as `short int`, it usually represents a 16-bit signed integer.

3. **long**: Also known as `long int`, it's typically a 32-bit or 64-bit signed integer depending on the platform.

4. **long long**: Introduced in C++11, this type represents at least a 64-bit signed integer.

#### Example:

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    short y = 20;
    long z = 1234567890;
    long long w = 987654321098765432;

    cout << "x: " << x << endl;
    cout << "y: " << y << endl;
    cout << "z: " << z << endl;
    cout << "w: " << w << endl;

    return 0;
}
```

### Floating-point Types

Floating-point types represent numbers with a fractional component.

#### Common Floating-point Types:

1. **float**: This typically represents a 32-bit floating-point number.

2. **double**: This represents a 64-bit floating-point number and is more precise than `float`.

#### Example:

```cpp
#include <iostream>
using namespace std;

int main() {
    float a = 3.14;
    double b = 2.718281828459045;

    cout << "a: " << a << endl;
    cout << "b: " << b << endl;

    return 0;
}
```

### Character Types

Character types represent single characters.

#### Common Character Types:

1. **char**: Represents a single byte character.

2. **wchar_t**: Represents a wide character (typically 16 or 32 bits). Used for extended character sets.

#### Example:

```cpp
#include <iostream>
using namespace std;

int main() {
    char c = 'A';
    wchar_t wc = L'€';

    cout << "c: " << c << endl;
    wcout << "wc: " << wc << endl; // Note: Use wcout for wide characters

    return 0;
}
```

### Boolean Type

The boolean type (`bool`) represents true or false values.

#### Example:

```cpp
#include <iostream>
using namespace std;

int main() {
    bool isTrue = true;
    bool isFalse = false;

    cout << "isTrue: " << isTrue << endl;
    cout << "isFalse: " << isFalse << endl;

    return 0;
}
```

