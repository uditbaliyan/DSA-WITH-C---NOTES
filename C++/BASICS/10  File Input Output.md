

### Reading from Files

To read from a file in C++, you need to:

1. Include the `<fstream>` header file for file operations.
2. Create an `ifstream` object (input file stream).
3. Open the file using the `open()` method.
4. Read from the file using standard input operations (e.g., `>>` for reading data).

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream inputFile;
    inputFile.open("example.txt");

    if (!inputFile) {
        cout << "Error opening file." << endl;
        return 1;
    }

    int number;
    while (inputFile >> number) {
        cout << "Read number: " << number << endl;
    }

    inputFile.close();

    return 0;
}
```

In this example, we open a file named `example.txt` for reading. We then use a loop to read integers from the file and print them to the console.

### Writing to Files

To write to a file in C++, you need to:

1. Include the `<fstream>` header file for file operations.
2. Create an `ofstream` object (output file stream).
3. Open the file using the `open()` method.
4. Write to the file using standard output operations (e.g., `<<` for writing data).

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream outputFile;
    outputFile.open("output.txt");

    if (!outputFile) {
        cout << "Error opening file." << endl;
        return 1;
    }

    outputFile << "Hello, World!" << endl;
    outputFile << "This is a test." << endl;

    outputFile.close();

    return 0;
}
```

In this example, we open a file named `output.txt` for writing. We then use `<<` to write strings to the file.

Remember to close the file using the `close()` method when you're done with it.

These examples demonstrate how to perform basic file input/output operations in C++. Keep in mind that error handling (checking if the file opened successfully) is important for robust file operations.