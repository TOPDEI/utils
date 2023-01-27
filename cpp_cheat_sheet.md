<link rel="stylesheet" type="text/css" href="style.css">

# C++ Cheat Sheet

### [Table of Contents](#table-of-contents)
- [Compiling and Executing C++](#compiling-and-executing-c++)
- [C++ Basics](#c++-basics)
  - [Variables](#variables)
  - [Input/Output](#inputoutput)
  - [Conditionals](#conditionals)
  - [Loops](#loops)
  - [Arrays](#arrays)
  - [Vectors](#vectors)
  - [Strings](#strings)
  - [Classes](#classes)
- [C++ Advanced Structures](#c++-advanced-structures)
  - [Queues](#queues)
  - [Stacks](#stacks)
  - [Priority Queues](#priority-queues)
  - [Sets](#sets)
  - [Maps](#maps)
- [C++ Standard Library Algorithms](#c++-standard-library-algorithms)
  - [Sorting](#sorting)
  - [Searching](#searching)
  - [Counting](#counting)
  - [Reversing](#reversing)
  - [Removing](#removing)
  - [Minimum and Maximum](#minimum-and-maximum)
  - [Lower and Upper Bounds](#lower-and-upper-bounds)
  - [Binary Search](#binary-search)
- [C++ Basic Programs](#c++-basic-programs)
  - [Hello World](#hello-world)
  - [Fibonacci](#fibonacci)
  - [Prime Number](#prime-number)
- [Big O Notation](#big-o-notation)
- [C++ Documentation](#c-documentation)

----------------
## <h2 id="compiling-and-executing-c++"> <a class="right-aligned" href="#table-of-contents">↩</a> Compiling and Executing C++</h2>

To compile and execute a C++ program, you need to use a compiler. A compiler is a program that translates C++ source code into machine language. The machine language is then executed by the computer. There are many compilers available for C++, including GCC, Clang, and Microsoft Visual C++. In this tutorial, we will use GCC, which is the GNU Compiler Collection. GCC is a free and open-source compiler that is available for Windows, Mac, and Linux.

To compile and execute a C++ program, you need to follow these steps:

1. Create a C++ source code file with a .cpp extension. For example, main.cpp.
2. Open a command prompt and navigate to the directory that contains your C++ source code file.
3. Type the following command to compile your C++ source code file:
```bash
g++ -std=c++17 -Wall main.cpp -o main
```
4. Type the following command to execute the output file:
```bash
./main
```

### Input/Output

To use a file as input, you can use the following command:
```bash
./main < input.txt
```

To use a file as output, you can use the following command:
```bash
./main > output.txt
```

To use a file as both input and output, you can use the following command:
```bash
./main < input.txt > output.txt
```

----------------

## <h2 id="c++-basics"> <a class="right-aligned" href="#table-of-contents">↩</a> C++ Basics</h2>

### Variables

In C++, there are various types of variables, including integer, character, floating point, double floating point, and boolean variables. Variables are able to store different types of information, and different types of variables can store different types of information.

C++ is a statically typed language, which means that all variables must be declared before they can be used. The compiler needs to know what type of data a variable will store, so that it can reserve the appropriate amount of memory and determine what operations can be performed on the variable. The general form of a variable declaration is:

```cpp
type variable_list;
```

Here, type must be a valid C++ data type including char, w_char, int, float, double, bool, or any user-defined object, etc. variable_list may consist of one or more identifier names separated by commas. Here are some examples of variable declarations:

```cpp
int    i, j, k;
char   c, ch;
float  f, salary;
double d;
```

-----------------

### Input/Output

C++ provides various ways to perform input and output operations. In this tutorial, we will learn about the following types of input/output:

- Standard Input/Output
- File Input/Output

#### Standard Input/Output

C++ provides two objects named cin and cout that are used to perform standard input and output operations. The cin object is used to read input from the standard input device (usually the keyboard) and the cout object is used to display output on the standard output device (usually the monitor).

The following program uses the cin and cout objects to read and display a number entered by the user:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int number;

    cout << "Enter an integer: ";
    cin >> number;

    cout << "You entered " << number;

    return 0;
}
```

#### File Input/Output

C++ provides two objects named fstream and ifstream that are used to perform file input and output operations. The fstream object is used to both read and write from/to files. The ifstream object is used to read from files and the ofstream object is used to write to files.

The following program uses the fstream object to read and display a number from a file:

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main()
{
    int number;

    ifstream in("number.txt");

    in >> number;

    cout << "The number is " << number;

    return 0;
}
```

-----------------

### Conditionals

C++ supports the usual logical conditions from mathematics:

- Less than: a < b
- Less than or equal to: a <= b
- Greater than: a > b
- Greater than or equal to: a >= b
- Equal to a == b
- Not Equal to: a != b

C++ uses the following logical operators to determine the conditions:

- Logical AND: &&
- Logical OR: ||
- Logical NOT: !

The following program uses a variable to store the inputted number. It then uses an if statement to check whether the number is positive or negative. If the number is positive, it is displayed as output. If the number is negative, the program displays a message:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int number;

    cout << "Enter an integer: ";
    cin >> number;

    // checks if the number is positive
    if (number > 0) {
        cout << "You entered a positive integer: " << number << endl;
    }
    // checks if the number is 0
    else if (number == 0) {
        cout << "You entered 0." << endl;
    }
    // if both test expressions are evaluated to false
    else {
        cout << "You entered a negative integer: " << number << endl;
    }

    cout << "This statement is always executed.";

    return 0;
}
```

-----------------


### Loops

C++ supports the usual control flow statements known from other programming languages, with some twists.

#### while loop

The while loop statement in C++ repeatedly executes a target statement as long as a given condition is true. The syntax of a while loop in C++ is:

```cpp
while (condition)
{
    // statement(s)
}
```

The following program uses a while loop to display the numbers from 1 to 10:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 1;

    // while loop from 1 to 10
    while (i <= 10) {
        cout << i << endl;
        ++i;
    }

    return 0;
}
```

#### for loop

The for loop is another control flow statement in C++ that allows code to be executed repeatedly.

The syntax of a for loop in C++ is:

```cpp
for (init; condition; increment)
{
    // statement(s)
}
```

The following program uses a for loop to display the numbers from 1 to 10:

```cpp
#include <iostream>
using namespace std;

int main()
{
    // for loop from 1 to 10
    for (int i = 1; i <= 10; ++i) {
        cout << i << endl;
    }

    return 0;
}
```

#### do...while loop

The do...while loop is very similar to the while loop. The difference is that the condition is evaluated at the end of the loop body. This means that the loop body is executed at least once, even if the condition is false, because the condition is not checked until after the loop body has been executed.

The syntax of a do...while loop in C++ is:

```cpp
do
{
    // statement(s)
}
while (condition);
```

The following program uses a do...while loop to display the numbers from 1 to 10:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 1;

    // do...while loop from 1 to 10
    do {
        cout << i << endl;
        ++i;
    } while (i <= 10);

    return 0;
}
```

-----------------

### Arrays

Hum... Don't use arrays. Use vectors instead. Arrays are a C thing.

-----------------

### Vectors

Vectors are sequence containers representing arrays that can change in size.

Just like arrays, vectors use contiguous storage locations for their elements, which means that their elements can also be accessed using offsets on regular pointers to its elements, and just as efficiently as in arrays. But unlike arrays, their size can change dynamically, with their storage being handled automatically by the container.

Internally, vectors use a dynamically allocated array to store their elements. This array may need to be reallocated in order to grow in size when new elements are inserted, which implies allocating a new array and moving all elements to it. This is a relatively expensive task in terms of processing time, and thus, vectors do not reallocate each time an element is added to the container.

Instead, vector containers may allocate some extra storage to accommodate for possible growth, and thus the container may have an actual capacity greater than the storage strictly needed to contain its elements (i.e., its size).

Accessing elements in a vector is done using the at() function or the [] operator. The at() function performs bounds checking, while the [] operator does not. The indexes of both functions start at 0.

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v = { 7, 5, 16, 8 };

    // Output the third element in the vector
    cout << "Third element: " << v.at(2) << endl;

    // Change the value of the third element
    v.at(2) = 100;

    cout << "New third element: " << v.at(2) << endl;

    v[0] = 200;

    cout << "New first element: " << v[0] << endl;

    return 0;
}
```

#### Declaring a vector

To declare a vector, use the following syntax:

```cpp
vector<type> name;
```

The following program declares a vector of integers:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v;

    return 0;
}
```

#### Initializing a vector

To initialize a vector, use the following syntax:

```cpp
vector<type> name = {value1, value2, ..., valueN};
```

The following program initializes a vector of integers:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v = { 7, 5, 16, 8 };

    return 0;
}
```

A vector can also be initialized using the push_back() function:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v;

    v.push_back(7);
    v.push_back(5);
    v.push_back(16);
    v.push_back(8);

    return 0;
}
```

Moreover, a vector can also be initialized with a certain number of elements, all with the same value:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // This will create a vector with 5 elements, all with the value 1
    vector<int> v(5, 1);
    // This will create a 3x4 matrix, all with the value 1
    vector<vector<int>> v2(3, vector<int>(4, 1));
    // This will create a vector of vectors, with 3 empty vectors
    vector<vector<int>> v3(3, vector<int>());
    return 0;
}
```

#### Iterators

Iterators are objects that point to elements in a range of elements. They are used to iterate over the elements of a container. Iterators are very similar to pointers, but they are not exactly the same. Iterators are used to access the elements of a container, while pointers are used to access the elements of a memory location.

Iterators are used to access the elements of a container. They are similar to pointers, but they are not exactly the same. Iterators are used to access the elements of a container, while pointers are used to access the elements of a memory location.


#### begin() and end()

The begin() and end() functions are used to get the beginning and ending positions of a container. These functions are used to iterate over the elements of a container.

The following program uses the begin() and end() functions to iterate over the elements of a vector:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v = { 7, 5, 16, 8 };

    // Iterate over the vector elements using begin() and end()
    for (auto i = v.begin(); i != v.end(); ++i)
        cout << *i << " ";

    return 0;
}
```

#### rbegin() and rend()

The rbegin() and rend() functions are used to get the reverse beginning and reverse ending positions of a container. These functions are used to iterate over the elements of a container in reverse order.

The following program uses the rbegin() and rend() functions to iterate over the elements of a vector in reverse order:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v = { 7, 5, 16, 8 };

    // Iterate over the vector elements in reverse order using rbegin() and rend()
    for (auto i = v.rbegin(); i != v.rend(); ++i)
        cout << *i << " ";

    return 0;
}
```

#### Operators

The following operators can be used to modify a vector:

| Operator | Description | Complexity |
| --- | --- | --- |
| `v.push_back(x)` | Adds an element to the end of the vector | O(1) |
| `v.pop_back()` | Removes the last element of the vector | O(1) |
| `v.insert(pos, x)` | Inserts an element at the specified position | O(n) |
| `v.erase(pos)` | Removes the element at the specified position | O(n) |
| `v.clear()` | Removes all elements from the vector | O(n) |
| `v.empty()` | Returns true if the vector is empty | O(1) |
| `v.size()` | Returns the number of elements in the vector | O(1) |
| `v.emplace_back(x)` | Inserts a new element at the end of the vector | O(1) |
| `v.emplace_front(x)` | Inserts a new element at the beginning of the vector | O(n) |

Example:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v = { 7, 5, 16, 8 };

    // Add an element to the end
    v.push_back(25);

    // Remove the last element
    v.pop_back();

    // Insert an element at the beginning
    v.insert(v.begin(), 13);

    // Erase the second element
    v.erase(v.begin() + 1);

    // Display the vector elements using begin() and end()
    for (auto i = v.begin(); i != v.end(); ++i)
        cout << *i << " ";
    
    cout << v.size() << endl;

    return 0;
}
```

-----------------

### Strings

A string is a sequence of characters. It is a data type that is used to store text. Strings are used to store text in C++. They are declared using the string data type. The string data type is defined in the string header file.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string str = "Hello World";
    cout << str;
    return 0;
}
```

#### String Operations

The following operations can be performed on strings:

| Operation | Description | Complexity |
| --- | --- | --- |
| + | Concatenates two strings | O(n) |
| += | Concatenates a string to another string | O(n) |
| == | Checks if two strings are equal | O(n) |
| != | Checks if two strings are not equal | O(n) |
| > | Checks if one string is greater than another string | O(n) |
| < | Checks if one string is less than another string | O(n) |
| >= | Checks if one string is greater than or equal to another string | O(n) |
| <= | Checks if one string is less than or equal to another string | O(n) |
| [] | Accesses a character at a specified position | O(1) |
| size() | Returns the number of characters in a string | O(1) |
| clear() | Removes all characters from a string | O(n) |
| empty() | Checks if a string is empty | O(1) |
| append() | Appends a string to another string | O(n) |
| insert() | Inserts a string at a specified position | O(n) |
| erase() | Removes a character at a specified position | O(n) |
| substr() | Returns a substring of a string | O(n) |

Example:

```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string str1 = "Hello";
    string str2 = "World";
    string str3 = str1 + str2;
    cout << str3 << endl; // HelloWorld
    str1 += str2;
    cout << str1 << endl; // HelloWorld

    if (str1 == str2)
        cout << "Strings are equal";
    else
        cout << "Strings are not equal";

    cout << str1.size() << endl; // 10

    string substr = str1.substr(2, 4);
    cout << substr << endl; // lloW

    return 0;
}
```

-----------------

### Classes

A class is a user-defined data type that can be used to group related variables and functions. It is a blueprint for creating objects. It is a collection of data members and member functions.

#### Creating a Class

The following program creates a class named Point:

```cpp
#include <iostream>
using namespace std;

class Point {
    public:
        int x;
        int y;
      
        Point(int x1, int y1) {
            x = x1;
            y = y1;
        }

        int sum() {
            return x + y;
        }
};

int main()
{
    Point p1(10, 15);
    cout << p1.sum() << endl;
    return 0;
}
```

-----------------

## <h2 id="c++-advanced-structures"> <a class="right-aligned" href="#table-of-contents">↩</a> C++ Advanced Structures</h2>

### Queues

A queue is a container that stores elements in a first-in-first-out (FIFO) manner. The following program creates a queue:

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> q;
    q.push(10);
    q.push(20);
    q.push(30);
    q.push(40);
    q.push(50);

    cout << q.front() << endl; // 10
    cout << q.back() << endl; // 50

    q.pop();
    cout << q.front() << endl; // 20

    return 0;
}
```

#### Queue Operations

The following operations can be performed on queues:

| Operation | Description | Complexity |
| --- | --- | --- |
| push() | Inserts a new element at the end of the queue | O(1) |
| pop() | Removes the first element of the queue | O(1) |
| front() | Returns the first element of the queue | O(1) |
| back() | Returns the last element of the queue | O(1) |
| empty() | Checks if the queue is empty | O(1) |
| size() | Returns the number of elements in the queue | O(1) |

### Stacks

A stack is a container that stores elements in a last-in-first-out (LIFO) manner. The following program creates a stack:

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main()
{
    stack<int> s;
    s.push(10);
    s.push(20);
    s.push(30);
    s.push(40);
    s.push(50);

    cout << s.top() << endl; // 50

    s.pop();
    cout << s.top() << endl; // 40

    return 0;
}
```

#### Stack Operations

The following operations can be performed on stacks:

| Operation | Description | Complexity |
| --- | --- | --- |
| push() | Inserts a new element at the top of the stack | O(1) |
| pop() | Removes the top element of the stack | O(1) |
| top() | Returns the top element of the stack | O(1) |
| empty() | Checks if the stack is empty | O(1) |
| size() | Returns the number of elements in the stack | O(1) |

### Priority Queues

A priority queue is a container that stores elements in a sorted manner. The following program creates a priority queue:

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    priority_queue<int> pq;
    pq.push(10);
    pq.push(20);
    pq.push(30);
    pq.push(40);
    pq.push(50);

    cout << pq.top() << endl; // 50

    pq.pop();
    cout << pq.top() << endl; // 40

    return 0;
}
```

On default, the priority queue sorts the elements in a descending order. To sort the elements in an ascending order, use the following code:

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

It is also possible to use a custom comparator to sort the elements. The following program creates a priority queue that sorts the elements in a defined order:

```cpp
#include <iostream>
#include <queue>
using namespace std;

class Compare {
    public:
        bool operator()(int a, int b) {
            // Custom comparator
        }
};

int main()
{
    priority_queue<int, vector<int>, Compare> pq;
    return 0;
}
```

Note: The operations that can be performed on priority queues are the same as those that can be performed on queues. However, the complexity of the operations is different. The complexity of the operations on priority queues is O(log n).

### Sets

A set is a container that stores unique elements in a sorted manner. The following program creates a set:

```cpp
#include <iostream>
#include <set>
using namespace std;

int main()
{
    set<int> s;
    s.insert(10);
    s.insert(20);
    s.insert(30);
    s.insert(40);
    s.insert(50);

    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " "; // 10 20 30 40 50

    return 0;
}
```

#### Set Operations

The following operations can be performed on sets:

| Operation | Description | Complexity |
| --- | --- | --- |
| insert() | Inserts a new element in the set | O(log n) |
| erase() | Removes an element from the set | O(log n) |
| find() | Returns an iterator to the element if it is found, otherwise returns an iterator to the end of the set | O(log n) |
| empty() | Checks if the set is empty | O(1) |
| size() | Returns the number of elements in the set | O(1) |

### Maps

A map is a container that stores elements in a key-value manner. The following program creates a map:

```cpp
#include <iostream>
#include <map>
using namespace std;

int main()
{
    map<int, string> m;
    m.insert({1, "Hello"});
    m.insert({2, "World"});
    m.insert({3, "!"});

    for (auto it = m.begin(); it != m.end(); it++)
        cout << it->first << " " << it->second << endl;
    // 1 Hello
    // 2 World
    // 3 !

    return 0;
}
```

#### Map Operations

The following operations can be performed on maps:

| Operation | Description | Complexity |
| --- | --- | --- |
| insert() | Inserts a new element in the map | O(log n) |
| erase() | Removes an element from the map | O(log n) |
| find() | Returns an iterator to the element if it is found, otherwise returns an iterator to the end of the map | O(log n) |
| empty() | Checks if the map is empty | O(1) |
| size() | Returns the number of elements in the map | O(1) |

-----------------

## <h2 id="c++-standard-library-algorithms"> <a class="right-aligned" href="#table-of-contents">↩</a> C++ Standard Library Algorithms</h2>

### Sorting

Complexity: O(n log n)

The following program sorts the elements of a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 50, 30, 20, 40};
    sort(v.begin(), v.end());
    for (auto it = v.begin(); it != v.end(); it++)
        cout << *it << " "; // 10 20 30 40 50
    return 0;
}
```

### Searching

Complexity: O(log n)

The following program searches for an element in a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    auto it = find(v.begin(), v.end(), 30);
    if (it != v.end())
        cout << "Element found" << endl;
    else
        cout << "Element not found" << endl;
    return 0;
}
```

### Counting

Complexity: O(n)

The following program counts the number of occurrences of an element in a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50, 30, 30};
    cout << count(v.begin(), v.end(), 30) << endl; // 3
    return 0;
}
```

### Reversing

Complexity: O(n)

The following program reverses the elements of a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    reverse(v.begin(), v.end());
    for (auto it = v.begin(); it != v.end(); it++)
        cout << *it << " "; // 50 40 30 20 10
    return 0;
}
```

### Removing

Complexity: O(n)

The following program removes an element from a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    v.erase(remove(v.begin(), v.end(), 30), v.end());
    for (auto it = v.begin(); it != v.end(); it++)
        cout << *it << " "; // 10 20 40 50
    return 0;
}
```

### Minimum and Maximum

Complexity: O(n)

The following program finds the minimum and maximum elements of a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    cout << *min_element(v.begin(), v.end()) << endl; // 10
    cout << *max_element(v.begin(), v.end()) << endl; // 50
    return 0;
}
```

### Lower and Upper Bounds

Complexity: O(log n)

The lower bound of an element is the first element that is not less than the given element.

The upper bound of an element is the first element that is greater than the given element.

Note: In case the given element is not present in the container, the lower bound is the first element that is greater than the given element and the upper bound is the first element that is not less than the given element.

The following program finds the lower and upper bound of an element in a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    auto it = lower_bound(v.begin(), v.end(), 30);
    cout << *it << endl; // 30
    it = upper_bound(v.begin(), v.end(), 30);
    cout << *it << endl; // 40
    return 0;
}
```

### Binary Search

Complexity: O(log n)

Binary search is a search algorithm that finds the position of a target value within a sorted array.

The following program performs binary search on a vector:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30, 40, 50};
    if (binary_search(v.begin(), v.end(), 30))
        cout << "Element found" << endl;
    else
        cout << "Element not found" << endl;
    return 0;
}
```

-----------------

## <h2 id="c++-basic-programs"> <a class="right-aligned" href="#table-of-contents">↩</a> C++ Basic Programs</h2>

### Hello World

The following program prints "Hello World":

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello World" << endl;
    return 0;
}
```

### Fibonacci Series

The following program prints the Fibonacci series:

```cpp
#include <iostream>
using namespace std;

int recursiveFibonacci(int n)
{
    if (n <= 1)
        return n;
    return recursiveFibonacci(n - 1) + recursiveFibonacci(n - 2);
}

int iterativeFibonacci(int n)
{
    int a = 0, b = 1, c, i;
    if (n == 0)
        return a;
    for (i = 2; i <= n; i++)
    {
        c = a + b;
        a = b;
        b = c;
    }
    return b;
}

int main()
{
    int n;
    cout << "Enter the number of terms: ";
    cin >> n;
    cout << "Recursive Fibonacci Series: ";
    for (int i = 0; i < n; i++)
        cout << recursiveFibonacci(i) << " ";
    cout << endl;
    cout << "Iterative Fibonacci Series: ";
    for (int i = 0; i < n; i++)
        cout << iterativeFibonacci(i) << " ";
    cout << endl;
    return 0;
}
```

### Prime Number

The following program checks if a number is prime or not:

```cpp
#include <iostream>
using namespace std;

bool isPrime(int n)
{
    if (n <= 1)
        return false;
    for (int i = 2; i < n; i++)
        if (n % i == 0)
            return false;
    return true;
}

int main()
{
    int n;
    cout << "Enter a number: ";
    cin >> n;
    if (isPrime(n))
        cout << n << " is a prime number" << endl;
    else
        cout << n << " is not a prime number" << endl;
    return 0;
}
```

-----------------

## <h2 id="big-o-notation"> <a class="right-aligned" href="#table-of-contents">↩</a> Big O Notation</h2>

Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. In computer science, Big O notation is used to classify algorithms according to how their run time or space requirements grow as the input size grows. Big O notation is also used to classify data structures according to their performance.

The following table shows the common Big O notations, in increasing order of complexity:

| Notation | Name | Description |
|----------|------|-------------|
| O(1) | Constant | An algorithm is said to have constant time complexity if the time taken by the algorithm remains the same irrespective of the size of the input. |
| O(log n) | Logarithmic | An algorithm is said to have logarithmic time complexity if the time taken by the algorithm increases at a slower rate than the size of the input. |
| O(n) | Linear | An algorithm is said to have linear time complexity if the time taken by the algorithm increases at the same rate as the size of the input. |
| O(n log n) | Log-linear | An algorithm is said to have log-linear time complexity if the time taken by the algorithm increases at a faster rate than the size of the input. |
| O(n^2) | Quadratic | An algorithm is said to have quadratic time complexity if the time taken by the algorithm increases at a faster rate than the size of the input. |
| O(n^3) | Cubic | An algorithm is said to have cubic time complexity if the time taken by the algorithm increases at a faster rate than the size of the input. |
| O(2^n) | Exponential | An algorithm is said to have exponential time complexity if the time taken by the algorithm increases at a faster rate than the size of the input. |
| O(n!) | Factorial | An algorithm is said to have factorial time complexity if the time taken by the algorithm increases at a faster rate than the size of the input. |

For example, if there is a time limit of 1 second, the value of n for which the algorithm will run in less than 1 second for each notation is as follows:

| Input Size | Time Complexity |
|------------|-----------------|
| 10 | O(n!) |
| 20 | O(2^n) |
| 500 | O(n^3) |
| 5000 | O(n^2) |
| 10^6 | O(n log n) |
| 10^8 | O(n) |
| 10^12 | O(log n) |
| 10^18 | O(1) |

-----------------

## C++ Documentation

* [C++ Reference](https://en.cppreference.com/w/)

[Back to Table of Contents](#table-of-contents)
