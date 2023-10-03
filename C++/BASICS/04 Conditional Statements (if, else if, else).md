

Conditional statements allow you to execute different blocks of code based on certain conditions.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 10;

    if (num > 10) {
        cout << "Num is greater than 10." << endl;
    } else if (num < 10) {
        cout << "Num is less than 10." << endl;
    } else {
        cout << "Num is equal to 10." << endl;
    }

    return 0;
}
```

In this example, the program checks the value of `num` and prints a message accordingly.

## Switch Statement

The switch statement allows you to select one of many code blocks to be executed.

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 2;

    switch (day) {
        case 1:
            cout << "Sunday" << endl;
            break;
        case 2:
            cout << "Monday" << endl;
            break;
        case 3:
            cout << "Tuesday" << endl;
            break;
        case 4:
            cout << "Wednesday" << endl;
            break;
        case 5:
            cout << "Thursday" << endl;
            break;
        case 6:
            cout << "Friday" << endl;
            break;
        case 7:
            cout << "Saturday" << endl;
            break;
        default:
            cout << "Invalid day" << endl;
    }

    return 0;
}
```

In this example, based on the value of `day`, the program executes the corresponding block of code. If none of the cases match, the `default` case is executed.

These are essential control flow statements in C++ that allow your program to make decisions based on conditions.