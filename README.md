# DSA

In C++, creating and working with 2D arrays can be done using various methods. Here’s a detailed guide to help you understand how to create, initialize, and manipulate 2D arrays in C++.

### Basic Static 2D Array

A static 2D array has fixed dimensions that are defined at compile time. Here's how you can declare, initialize, and print a static 2D array:

```
cppCopy code#include 
using namespace std;

int main() {
    // Declare and initialize a static 2D array with 3 rows and 4 columns
    const int rows = 3;
    const int cols = 4;
    int array2D[rows][cols] = { 
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };

    // Print the array
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << array2D[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

### Dynamic 2D Array

If the dimensions of the 2D array are not known at compile time or if you need to allocate memory dynamically, you can use pointers. Here’s how to create and work with a dynamically allocated 2D array:

```
cppCopy code#include 
using namespace std;

int main() {
    int rows = 3;
    int cols = 4;

    // Create a pointer to a pointer (array of pointers)
    int** array2D = new int*[rows];
    
    // Allocate memory for each row
    for (int i = 0; i < rows; ++i) {
        array2D[i] = new int[cols];
    }

    // Initialize the 2D array
    int value = 1;
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            array2D[i][j] = value++;
        }
    }

    // Print the 2D array
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << array2D[i][j] << " ";
        }
        cout << endl;
    }

    // Deallocate the memory
    for (int i = 0; i < rows; ++i) {
        delete[] array2D[i];
    }
    delete[] array2D;

    return 0;
}
```

### Using std::vector for 2D Arrays

A more modern and flexible way to work with 2D arrays in C++ is to use`std::vector`. This approach handles memory management automatically and is generally preferred for its ease of use and safety.

```
cppCopy code#include 
#include 
using namespace std;

int main() {
    // Define the dimensions
    int rows = 3;
    int cols = 4;

    // Create a 2D vector
    vector> array2D(rows, vector(cols));

    // Initialize the 2D vector
    int value = 1;
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            array2D[i][j] = value++;
        }
    }

    // Print the 2D vector
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << array2D[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

### Summary


  - **Static 2D Array**: Simple and fixed size; uses`int array2D[rows][cols]`.
  - **Dynamic 2D Array**: Flexible size; use pointers and`new`/`delete`for memory management.
  - **`std::vector`**: Modern and safe approach; handles memory management automatically and supports dynamic sizes.

Each method has its use cases, so choose the one that best fits your needs.
