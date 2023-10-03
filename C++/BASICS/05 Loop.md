

## while Loop

The `while` loop allows you to repeatedly execute a block of code as long as a condition is true.

```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 0;

    while (count < 5) {
        cout << "Count: " << count << endl;
        count++;
    }

    return 0;
}
```

In this example, the program will print the value of `count` and increment it by 1 in each iteration as long as `count` is less than 5.

## for Loop

The `for` loop is used to iterate a specific number of times.

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "i: " << i << endl;
    }

    return 0;
}
```

In this example, the loop initializes `i` to 0, and iterates as long as `i` is less than 5, incrementing `i` by 1 in each iteration.

## do-while Loop

The `do-while` loop is similar to the `while` loop, but it guarantees that the code block is executed at least once before checking the condition.

```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 0;

    do {
        cout << "Count: " << count << endl;
        count++;
    } while (count < 5);

    return 0;
}
```

In this example, the program will execute the code block at least once, even if `count` is not less than 5 initially.

## break and continue Statements

`break` and `continue` are control flow statements used within loops.

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        if (i == 3) {
            break; // Exit the loop when i is 3
        }
        cout << "i: " << i << endl;
    }

    for (int j = 0; j < 5; j++) {
        if (j == 2) {
            continue; // Skip the rest of the loop body when j is 2
        }
        cout << "j: " << j << endl;
    }

    return 0;
}
```

In the first loop, when `i` reaches 3, the `break` statement is executed, and the loop is exited. In the second loop, when `j` is 2, the `continue` statement skips the rest of the loop body and moves to the next iteration.

These are the basic looping constructs and control flow statements in C++, allowing you to control the flow of your program based on conditions and repetitions.