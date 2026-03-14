# C++ Master Cheat Sheet 📘
### Beginner se Advanced — Complete Revision Guide (Hinglish)

> **Style:** Explanations Hinglish mein hain (English + simple Hindi in Roman script). Code examples simple aur correct hain.

---

## TABLE OF CONTENTS

| # | Section |
|---|---------|
| 1 | [Introduction to C++](#section-1--introduction-to-c) |
| 2 | [Basic Language Elements](#section-2--basic-language-elements) |
| 3 | [Preprocessor Directives](#section-3--preprocessor-directives) |
| 4 | [Header Files](#section-4--header-files) |
| 5 | [Data Types & Variables](#section-5--data-types--variables) |
| 6 | [Operators](#section-6--operators) |
| 7 | [Control Flow](#section-7--control-flow) |
| 8 | [Functions](#section-8--functions) |
| 9 | [Arrays & Strings](#section-9--arrays--strings) |
| 10 | [Pointers & References](#section-10--pointers--references) |
| 11 | [Object-Oriented Programming (OOP)](#section-11--object-oriented-programming-oop) |
| 12 | [Templates](#section-12--templates) |
| 13 | [Standard Template Library (STL)](#section-13--standard-template-library-stl) |
| 14 | [Exception Handling](#section-14--exception-handling) |
| 15 | [File I/O](#section-15--file-io) |
| 16 | [Modern C++ (C++11/14/17/20)](#section-16--modern-c-c11141720-features) |

---

## SECTION 1 — Introduction to C++

### What is C++?
C++ ek **general-purpose programming language** hai jo C language ka extended version hai. Isme object-oriented, procedural, aur generic programming ka support milta hai.

### History
| Year | Event |
|------|-------|
| 1979 | Bjarne Stroustrup ne "C with Classes" banaya |
| 1983 | Naam C++ rakha gaya |
| 1998 | C++98 — pehla ISO standard |
| 2011 | C++11 — bade changes (auto, lambdas, smart pointers) |
| 2014 | C++14 — small improvements |
| 2017 | C++17 — structured bindings, filesystem |
| 2020 | C++20 — concepts, coroutines, ranges |

### Features of C++
- **Object-Oriented** — Class, Object, Inheritance, Polymorphism
- **Fast & Efficient** — Low-level memory control
- **Portable** — Code zyada platforms pe chalti hai
- **Rich Standard Library** — STL available hai
- **Multi-paradigm** — OOP + Procedural + Generic

### Compilation Process
```
Source Code (.cpp)
       ↓
  Preprocessor   ← handles #include, #define
       ↓
   Compiler       ← translates to assembly/object code (.o)
       ↓
   Linker         ← combines object files + libraries
       ↓
  Executable (.exe / a.out)
```

### Structure of a C++ Program

```cpp
#include <iostream>   // Header file include karo

using namespace std;  // std namespace use karo

int main() {          // main function — program yahan se start hota hai
    cout << "Hello, World!" << endl;  // output print karo
    return 0;         // 0 = successful execution
}
```

**Output:**
```
Hello, World!
```

**Important Notes:**
- `main()` function har C++ program mein hona zaroori hai
- `cout` — character output (screen pe print karta hai)
- `endl` — newline deta hai aur buffer flush karta hai
- `return 0` — OS ko batata hai program successfully chala

---

## SECTION 2 — Basic Language Elements

### Tokens
**Definition:** Token C++ ka sabse chhota meaningful unit hai. Compiler source code ko tokens mein todta hai.

Types of tokens:
1. Keywords
2. Identifiers
3. Literals
4. Operators
5. Punctuators (`,`, `;`, `{`, `}`)

---

### Identifiers
**Definition:** Identifier naam hota hai — variable, function, class ka. Programmer khud define karta hai.

**Rules:**
- Sirf letters (a-z, A-Z), digits (0-9), aur underscore (`_`) use kar sakte ho
- Digit se start NAHI ho sakta
- Keyword nahi ho sakta
- Case-sensitive hai (`age` aur `Age` alag hain)

```cpp
int age = 25;       // 'age' ek valid identifier hai
float _salary;      // valid — underscore se shuru ho sakta hai
// int 2name;       // INVALID — digit se shuru nahi kar sakte
```

---

### Keywords
**Definition:** Keywords reserved words hain jo C++ ke liye predefined meaning rakhte hain. Inhe identifier ke roop mein use nahi kar sakte.

**Common Keywords:**

| Category | Keywords |
|----------|---------|
| Data types | `int`, `float`, `double`, `char`, `bool`, `void` |
| Control | `if`, `else`, `switch`, `case`, `break`, `continue`, `return` |
| Loops | `for`, `while`, `do` |
| OOP | `class`, `struct`, `public`, `private`, `protected`, `virtual`, `this` |
| Memory | `new`, `delete`, `sizeof` |
| Other | `const`, `static`, `extern`, `typedef`, `namespace`, `using` |

---

### Literals
**Definition:** Literal ek fixed value hai jo directly source code mein likhi jaati hai.

```cpp
int a = 10;         // integer literal
float b = 3.14f;    // floating-point literal
char c = 'A';       // character literal
bool d = true;      // boolean literal
string s = "Hello"; // string literal

// Integer literal formats
int hex = 0xFF;     // hexadecimal
int oct = 017;      // octal
int bin = 0b1010;   // binary (C++14)
```

---

### Comments
**Definition:** Comments wo text hai jo compiler ignore karta hai — code ko explain karne ke liye use hota hai.

```cpp
// Yeh single-line comment hai

/*
   Yeh multi-line
   comment hai
*/

/**
 * Yeh documentation comment hai (Doxygen style)
 * @param x input value
 */
```

**Important Note:** Comments runtime pe execute nahi hote.

---

### Whitespace
**Definition:** Spaces, tabs, newlines — compiler inhe ignore karta hai (strings ke andar chodke). Code readable banane ke liye use hota hai.

---

### Statements
**Definition:** Statement ek complete instruction hai jo `;` se end hoti hai.

```cpp
int x = 5;          // declaration statement
x = x + 1;          // expression statement
return 0;           // jump statement
```

---

### Blocks
**Definition:** Block `{}` curly braces ke andar code ka group hota hai.

```cpp
{
    int x = 10;  // x sirf is block ke andar visible hai
    cout << x;
}
// x yahan access nahi ho sakta
```

---

## SECTION 3 — Preprocessor Directives

**Definition:** Preprocessor directives `#` se start hoti hain aur compilation se **pehle** process hoti hain. Semicolon nahi lagta.

---

### `#include` — Header File Include Karo

```cpp
#include <iostream>      // standard library (angle brackets)
#include "myfile.h"      // user-defined header (double quotes)
```

**Note:** `<>` system/standard headers ke liye; `""` apne project ke headers ke liye.

---

### `#define` — Macro Define Karo

```cpp
#define PI 3.14159
#define MAX(a, b) ((a) > (b) ? (a) : (b))  // function-like macro

int main() {
    float area = PI * 5 * 5;
    cout << MAX(3, 7);  // output: 7
}
```

**Common Mistake:** Macro mein `=` mat lagao — `#define PI = 3.14` galat hai!

---

### `#undef` — Macro Undefine Karo

```cpp
#define LIMIT 100
// ... code ...
#undef LIMIT          // LIMIT ko remove kar do
#define LIMIT 200     // naya define kar sakte hain
```

---

### `#ifdef` / `#ifndef` — Conditional Compilation

```cpp
#define DEBUG

#ifdef DEBUG                    // agar DEBUG defined hai
    cout << "Debug mode on\n";
#endif

#ifndef RELEASE                 // agar RELEASE defined NAHI hai
    cout << "Not release build\n";
#endif
```

---

### `#if` / `#else` / `#elif` / `#endif`

```cpp
#define VERSION 2

#if VERSION == 1
    cout << "Version 1\n";
#elif VERSION == 2
    cout << "Version 2\n";   // yeh execute hoga
#else
    cout << "Unknown version\n";
#endif
```

---

### `#pragma` — Compiler-Specific Instructions

```cpp
#pragma once              // header guard — file ko ek baar hi include karo

#pragma warning(disable:4996)  // specific warning disable karo (MSVC)
```

**Note:** `#pragma once` zyada commonly use hota hai `#ifndef` guard ki jagah.

---

### Header Guard Pattern (Alternative to `#pragma once`)

```cpp
// myheader.h
#ifndef MYHEADER_H
#define MYHEADER_H

// header ka content yahan

#endif // MYHEADER_H
```

---

## SECTION 4 — Header Files

**Definition:** Header files mein function declarations, class definitions, constants hote hain. Extension `.h` ya `.hpp` hoti hai.

### Common Standard Headers

| Header | Purpose | Common Elements |
|--------|---------|-----------------|
| `<iostream>` | Input/Output | `cin`, `cout`, `cerr`, `endl` |
| `<string>` | String class | `string`, `getline()` |
| `<vector>` | Dynamic array | `vector<T>` |
| `<array>` | Fixed array | `array<T,N>` |
| `<list>` | Linked list | `list<T>` |
| `<map>` | Key-value pairs | `map<K,V>`, `multimap` |
| `<unordered_map>` | Hash map | `unordered_map<K,V>` |
| `<set>` | Unique sorted elements | `set<T>`, `multiset` |
| `<unordered_set>` | Hash set | `unordered_set<T>` |
| `<stack>` | Stack (LIFO) | `stack<T>` |
| `<queue>` | Queue (FIFO) | `queue<T>`, `priority_queue` |
| `<algorithm>` | Algorithms | `sort()`, `find()`, `reverse()` |
| `<cmath>` | Math functions | `sqrt()`, `pow()`, `abs()` |
| `<cstdlib>` | C utilities | `rand()`, `exit()`, `atoi()` |
| `<cstring>` | C-string functions | `strlen()`, `strcpy()`, `strcmp()` |
| `<fstream>` | File I/O | `ifstream`, `ofstream`, `fstream` |
| `<sstream>` | String streams | `stringstream`, `istringstream` |
| `<stdexcept>` | Exception classes | `runtime_error`, `logic_error` |
| `<memory>` | Smart pointers | `unique_ptr`, `shared_ptr` |
| `<thread>` | Threading | `thread`, `mutex` |
| `<chrono>` | Time | `duration`, `time_point` |
| `<functional>` | Function objects | `function<>`, `bind()` |
| `<iterator>` | Iterators | Iterator types |
| `<numeric>` | Numeric ops | `accumulate()`, `iota()` |
| `<limits>` | Type limits | `numeric_limits<T>` |
| `<cassert>` | Assertions | `assert()` |
| `<typeinfo>` | Type info | `typeid()` |

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    vector<int> v = {5, 3, 1, 4, 2};
    sort(v.begin(), v.end());          // algorithm se sort
    for (int x : v) cout << x << " "; // 1 2 3 4 5
    return 0;
}
```

---

## SECTION 5 — Data Types & Variables

### Fundamental Data Types

| Type | Size | Range | Example |
|------|------|-------|---------|
| `bool` | 1 byte | true/false | `bool b = true;` |
| `char` | 1 byte | -128 to 127 | `char c = 'A';` |
| `unsigned char` | 1 byte | 0 to 255 | |
| `short` | 2 bytes | -32768 to 32767 | |
| `int` | 4 bytes | ~-2.1B to 2.1B | `int x = 10;` |
| `unsigned int` | 4 bytes | 0 to ~4.2B | |
| `long` | 4/8 bytes | platform dependent | |
| `long long` | 8 bytes | ±9.2 × 10^18 | `long long n = 1e18;` |
| `float` | 4 bytes | ~±3.4 × 10^38 | `float f = 3.14f;` |
| `double` | 8 bytes | ~±1.7 × 10^308 | `double d = 3.14;` |
| `long double` | 12/16 bytes | higher precision | |
| `void` | 0 | no value | function return type |

```cpp
#include <iostream>
#include <limits>
using namespace std;

int main() {
    cout << "int max: " << numeric_limits<int>::max() << endl;
    cout << "double max: " << numeric_limits<double>::max() << endl;
    return 0;
}
```

---

### Variable Declaration & Initialization

```cpp
int x;              // declaration (garbage value)
int y = 10;         // copy initialization
int z(20);          // direct initialization
int w{30};          // uniform initialization (C++11) — preferred!
auto a = 3.14;      // type deduction (C++11)

// Multiple variables
int p = 1, q = 2, r = 3;
```

**Common Mistake:** Uninitialized variable use karna — undefined behavior hota hai!

---

### `const` & `constexpr`

```cpp
const int MAX = 100;        // runtime constant — value change nahi hogi
constexpr int SIZE = 256;   // compile-time constant (C++11)

// const pointer
const int* ptr1 = &x;   // pointer to const int (data change nahi)
int* const ptr2 = &x;   // const pointer (address change nahi)
const int* const ptr3 = &x; // dono const
```

---

### Type Casting

```cpp
int a = 10, b = 3;
double result = (double)a / b;           // C-style cast
double result2 = static_cast<double>(a) / b; // C++ style (preferred)

// C++ cast operators
static_cast<T>(expr)       // safe type conversion
dynamic_cast<T*>(ptr)      // polymorphic downcast (with RTTI)
const_cast<T*>(ptr)        // const remove karo
reinterpret_cast<T*>(ptr)  // low-level reinterpretation
```

---

### `sizeof` Operator

```cpp
cout << sizeof(int)    << endl;  // 4
cout << sizeof(double) << endl;  // 8
cout << sizeof(char)   << endl;  // 1

int arr[10];
cout << sizeof(arr) << endl;     // 40 (10 * 4)
```

---

### `auto` & `decltype` (C++11)

```cpp
auto x = 42;           // int
auto y = 3.14;         // double
auto z = "hello";      // const char*

int a = 5;
decltype(a) b = 10;    // b ka type 'int' hai (a ki type se)
decltype(a + 0.0) c;   // double
```

---

## SECTION 6 — Operators

### Arithmetic Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| `+` | Addition | `a + b` |
| `-` | Subtraction | `a - b` |
| `*` | Multiplication | `a * b` |
| `/` | Division | `a / b` |
| `%` | Modulus (remainder) | `a % b` |
| `++` | Increment | `a++`, `++a` |
| `--` | Decrement | `a--`, `--a` |

```cpp
int a = 10, b = 3;
cout << a + b;  // 13
cout << a / b;  // 3 (integer division!)
cout << a % b;  // 1
```

**Common Mistake:** `int/int = int` — `10/3 = 3`, NOT `3.33`

---

### Relational (Comparison) Operators

| Operator | Meaning |
|----------|---------|
| `==` | Equal to |
| `!=` | Not equal to |
| `<` | Less than |
| `>` | Greater than |
| `<=` | Less than or equal |
| `>=` | Greater than or equal |

---

### Logical Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| `&&` | Logical AND | `a && b` |
| `\|\|` | Logical OR | `a \|\| b` |
| `!` | Logical NOT | `!a` |

---

### Bitwise Operators

| Operator | Meaning |
|----------|---------|
| `&` | Bitwise AND |
| `\|` | Bitwise OR |
| `^` | Bitwise XOR |
| `~` | Bitwise NOT |
| `<<` | Left shift |
| `>>` | Right shift |

```cpp
int a = 5;  // 0101
int b = 3;  // 0011
cout << (a & b);   // 0001 = 1
cout << (a | b);   // 0111 = 7
cout << (a ^ b);   // 0110 = 6
cout << (a << 1);  // 1010 = 10 (x2)
cout << (a >> 1);  // 0010 = 2  (÷2)
```

---

### Assignment Operators

```cpp
x = 5;     // simple
x += 3;    // x = x + 3
x -= 2;    // x = x - 2
x *= 4;    // x = x * 4
x /= 2;    // x = x / 2
x %= 3;    // x = x % 3
x &= 0xF;  // bitwise AND assign
x |= 0x1;  // bitwise OR assign
x ^= 0x1;  // bitwise XOR assign
x <<= 1;   // left shift assign
x >>= 1;   // right shift assign
```

---

### Ternary (Conditional) Operator

```cpp
// Syntax: condition ? value_if_true : value_if_false
int max = (a > b) ? a : b;
string result = (marks >= 33) ? "Pass" : "Fail";
```

---

### Operator Precedence (High to Low)

| Level | Operators |
|-------|-----------|
| Highest | `::`, `()`, `[]`, `.`, `->`, `++`(post), `--`(post) |
| Unary | `!`, `~`, `++`(pre), `--`(pre), `-`(unary), `*`, `&`, `sizeof`, cast |
| Multiplicative | `*`, `/`, `%` |
| Additive | `+`, `-` |
| Shift | `<<`, `>>` |
| Relational | `<`, `<=`, `>`, `>=` |
| Equality | `==`, `!=` |
| Bitwise | `&`, `^`, `\|` |
| Logical | `&&`, `\|\|` |
| Ternary | `?:` |
| Assignment | `=`, `+=`, `-=`, etc. |
| Lowest | `,` |

---

## SECTION 7 — Control Flow

### `if` / `else if` / `else`

```cpp
int marks = 75;

if (marks >= 90) {
    cout << "A Grade";
} else if (marks >= 75) {
    cout << "B Grade";  // yeh print hoga
} else if (marks >= 60) {
    cout << "C Grade";
} else {
    cout << "Fail";
}
```

---

### `switch` Statement

```cpp
int day = 3;

switch (day) {
    case 1:
        cout << "Monday";
        break;
    case 2:
        cout << "Tuesday";
        break;
    case 3:
        cout << "Wednesday";  // yeh print hoga
        break;
    default:
        cout << "Other day";
}
```

**Common Mistake:** `break` bhool jana — fall-through hota hai!

---

### `for` Loop

```cpp
// Basic for loop
for (int i = 0; i < 5; i++) {
    cout << i << " ";  // 0 1 2 3 4
}

// Range-based for loop (C++11)
vector<int> v = {1, 2, 3, 4, 5};
for (int x : v) {
    cout << x << " ";
}

// Range-based with auto
for (auto& elem : v) {  // & for modification
    elem *= 2;
}
```

---

### `while` Loop

```cpp
int i = 0;
while (i < 5) {
    cout << i << " ";  // 0 1 2 3 4
    i++;
}
```

---

### `do-while` Loop

```cpp
int i = 0;
do {
    cout << i << " ";  // pehle execute hota hai, phir condition check
    i++;
} while (i < 5);
```

**Note:** `do-while` minimum ek baar zaroor execute hota hai.

---

### `break` aur `continue`

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 3) continue;  // 3 skip karo
    if (i == 7) break;     // 7 pe loop band karo
    cout << i << " ";      // 0 1 2 4 5 6
}
```

---

### `goto` Statement (Avoid karo!)

```cpp
goto label;
// yeh code skip hoga
label:
cout << "Jumped here!";
```

**Note:** `goto` use karna bad practice hai — avoid karo!

---

## SECTION 8 — Functions

### Function Definition & Declaration

```cpp
// Declaration (prototype)
int add(int a, int b);

// Definition
int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(3, 4);  // 7
    cout << result;
    return 0;
}
```

---

### Function Parameters

```cpp
// Pass by value (copy banta hai)
void increment(int x) {
    x++;  // original change nahi hota
}

// Pass by reference (original change hota hai)
void increment(int& x) {
    x++;  // original change hota hai
}

// Pass by pointer
void increment(int* x) {
    (*x)++;
}

// Const reference (read-only, efficient for large objects)
void print(const string& s) {
    cout << s;
}
```

---

### Default Arguments

```cpp
void greet(string name, string msg = "Hello") {
    cout << msg << ", " << name << "!" << endl;
}

greet("Rahul");           // Hello, Rahul!
greet("Priya", "Namaste"); // Namaste, Priya!
```

**Rule:** Default arguments right se left ki taraf define hone chahiye.

---

### Function Overloading

```cpp
int add(int a, int b) { return a + b; }
double add(double a, double b) { return a + b; }
int add(int a, int b, int c) { return a + b + c; }

// Compiler parameter types/count se decide karta hai
cout << add(1, 2);          // int version
cout << add(1.5, 2.5);      // double version
cout << add(1, 2, 3);       // 3-param version
```

---

### Inline Functions

```cpp
inline int square(int x) {
    return x * x;  // function call overhead avoid hota hai
}
```

**Note:** Compiler `inline` hint ko ignore kar sakta hai.

---

### Recursion

```cpp
int factorial(int n) {
    if (n <= 1) return 1;  // base case
    return n * factorial(n - 1);  // recursive case
}

int fibonacci(int n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

cout << factorial(5);   // 120
cout << fibonacci(7);   // 13
```

---

### Lambda Functions (C++11)

```cpp
// Syntax: [capture](params) -> return_type { body }

auto add = [](int a, int b) { return a + b; };
cout << add(3, 4);  // 7

// Capture variables
int x = 10;
auto addX = [x](int a) { return a + x; };  // x copy se capture
auto addXRef = [&x](int a) { return a + x; }; // x reference se

// [=] — all variables copy se
// [&] — all variables reference se
auto f = [=]() { cout << x; };

// Lambda with STL
vector<int> v = {3, 1, 4, 1, 5};
sort(v.begin(), v.end(), [](int a, int b) { return a > b; }); // descending
```

---

### `std::function` (C++11)

```cpp
#include <functional>

function<int(int, int)> op;

op = [](int a, int b) { return a + b; };
cout << op(3, 4);  // 7

op = [](int a, int b) { return a * b; };
cout << op(3, 4);  // 12
```

---

## SECTION 9 — Arrays & Strings

### C-Style Arrays

```cpp
int arr[5] = {1, 2, 3, 4, 5};  // size 5 ka array
int arr2[5] = {1, 2};           // baki elements 0 se initialize
int arr3[] = {1, 2, 3};         // size auto infer hoti hai

cout << arr[0];   // 1 (0-indexed)
cout << arr[4];   // 5

// Array size
int size = sizeof(arr) / sizeof(arr[0]);  // 5

// 2D Array
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
cout << matrix[1][2];  // 6
```

---

### `std::array` (C++11) — Preferred

```cpp
#include <array>

array<int, 5> arr = {1, 2, 3, 4, 5};
cout << arr[2];          // 3
cout << arr.at(2);       // 3 (bounds checking ke saath)
cout << arr.size();      // 5
cout << arr.front();     // 1
cout << arr.back();      // 5
arr.fill(0);             // sab 0 ho jaate hain
```

---

### `std::vector` — Dynamic Array

```cpp
#include <vector>

vector<int> v;              // empty vector
vector<int> v2(5, 0);       // size 5, sab 0
vector<int> v3 = {1, 2, 3}; // initializer list

v.push_back(10);    // end mein add
v.push_back(20);
v.pop_back();       // end se remove

v.insert(v.begin() + 1, 15);  // index 1 pe insert
v.erase(v.begin() + 1);       // index 1 se remove

cout << v.size();    // current elements
cout << v.capacity(); // allocated memory
v.reserve(100);      // memory pre-allocate

// Iterate
for (int x : v) cout << x << " ";
for (int i = 0; i < v.size(); i++) cout << v[i] << " ";
```

---

### C-Style Strings

```cpp
#include <cstring>

char name[] = "Rahul";
char name2[20] = "Priya";

strlen(name);          // 5 (null terminator nahi ginat)
strcpy(name2, name);   // name2 mein copy
strcat(name2, "!");    // concatenate
strcmp(name, name2);   // 0 = equal, <0 = less, >0 = greater
```

---

### `std::string` — Preferred

```cpp
#include <string>

string s = "Hello";
string s2("World");

s + " " + s2;           // "Hello World" (concatenation)
s.length();             // 5
s.size();               // 5 (same as length)
s[0];                   // 'H'
s.at(0);                // 'H' (bounds check)
s.substr(1, 3);         // "ell" (pos=1, len=3)
s.find("ll");           // 2 (position)
s.find("xyz");          // string::npos (not found)
s.replace(0, 5, "Hi");  // "Hi"
s.empty();              // false
s.clear();              // khali kar do
s.append(" there");     // end mein add
s.insert(2, "XY");      // index 2 pe "XY" insert
s.erase(2, 2);          // index 2 se 2 characters remove
s.compare(s2);          // 0 if equal
s.c_str();              // C-style string pointer

// String to number
int n = stoi("42");
double d = stod("3.14");
long l = stol("1234567");

// Number to string
string ns = to_string(42);

// Input with spaces
string line;
getline(cin, line);
```

---

## SECTION 10 — Pointers & References

### Pointers

**Definition:** Pointer ek variable hai jo kisi doosre variable ka **memory address** store karta hai.

```cpp
int x = 10;
int* ptr = &x;   // ptr mein x ka address hai

cout << x;       // 10 (value)
cout << &x;      // 0x... (address of x)
cout << ptr;     // 0x... (same address)
cout << *ptr;    // 10 (dereference — value at address)

*ptr = 20;       // x ki value change ho gayi
cout << x;       // 20
```

---

### Pointer Arithmetic

```cpp
int arr[] = {10, 20, 30, 40, 50};
int* ptr = arr;  // arr ka naam hi pehle element ka address hai

cout << *ptr;        // 10
cout << *(ptr + 1);  // 20
cout << *(ptr + 2);  // 30

ptr++;
cout << *ptr;  // 20
```

---

### Null Pointer

```cpp
int* ptr = nullptr;  // C++11 style (preferred)
int* ptr2 = NULL;    // C style
int* ptr3 = 0;       // avoid

if (ptr != nullptr) {
    cout << *ptr;  // safe hai
}
```

**Common Mistake:** Null pointer dereference — program crash hota hai!

---

### Dynamic Memory Allocation

```cpp
// Single variable
int* p = new int;      // allocate
*p = 42;
delete p;              // free karo — ZAROORI HAI!
p = nullptr;           // dangling pointer avoid karo

// With initialization
int* p2 = new int(100);
delete p2;

// Array
int* arr = new int[10];
arr[0] = 1;
delete[] arr;  // array ke liye delete[] use karo
arr = nullptr;
```

**Common Mistakes:**
- `delete` ke baad use karna (dangling pointer)
- `new[]` ke liye `delete` use karna (should be `delete[]`)
- Memory leak — `delete` bhool jaana

---

### Smart Pointers (C++11) — Use These!

```cpp
#include <memory>

// unique_ptr — single ownership
unique_ptr<int> up = make_unique<int>(42);
cout << *up;  // 42
// automatically delete hota hai scope ke baad

// shared_ptr — shared ownership (reference counting)
shared_ptr<int> sp1 = make_shared<int>(100);
shared_ptr<int> sp2 = sp1;  // dono same object point karte hain
cout << sp1.use_count();  // 2

// weak_ptr — circular reference prevent karta hai
weak_ptr<int> wp = sp1;
if (auto locked = wp.lock()) {
    cout << *locked;
}
```

---

### References

**Definition:** Reference ek existing variable ka doosra naam (alias) hota hai. Pointer ki tarah nahi hota.

```cpp
int x = 10;
int& ref = x;  // ref, x ka alias hai

ref = 20;      // x bhi 20 ho gaya
cout << x;     // 20

// Reference vs Pointer differences:
// 1. Reference null nahi ho sakta
// 2. Reference initialize karna zaroori hai
// 3. Reference reseated nahi hota (doosre variable ko point nahi kar sakta)
// 4. Syntax simpler hai (*, & operators nahi chahiye dereference ke liye)
```

---

### `const` with Pointers

```cpp
int a = 10, b = 20;

const int* p1 = &a;   // pointer to const — data change nahi
// *p1 = 5;           // ERROR!
p1 = &b;              // OK — address change ho sakta hai

int* const p2 = &a;   // const pointer — address change nahi
*p2 = 5;              // OK — data change ho sakta hai
// p2 = &b;           // ERROR!

const int* const p3 = &a;  // dono const
```

---

## SECTION 11 — Object-Oriented Programming (OOP)

### Class & Object

```cpp
class Car {
private:                    // sirf class ke andar access
    string brand;
    int speed;

public:                     // bahar se bhi access
    // Constructor
    Car(string b, int s) : brand(b), speed(s) {}

    // Member functions (methods)
    void accelerate(int inc) {
        speed += inc;
    }

    void display() const {  // const — object modify nahi karta
        cout << brand << ": " << speed << " km/h\n";
    }

    // Getter
    int getSpeed() const { return speed; }

    // Setter
    void setSpeed(int s) {
        if (s >= 0) speed = s;
    }
};

int main() {
    Car c1("Toyota", 100);  // object banana
    c1.accelerate(50);
    c1.display();           // Toyota: 150 km/h

    Car* cp = new Car("Honda", 80);
    cp->display();          // pointer se access
    delete cp;
    return 0;
}
```

---

### Constructors & Destructors

```cpp
class MyClass {
public:
    int value;

    MyClass() : value(0) {}           // default constructor
    MyClass(int v) : value(v) {}      // parameterized constructor
    MyClass(const MyClass& other) : value(other.value) {}  // copy constructor
    MyClass(MyClass&& other) noexcept : value(other.value) { // move constructor
        other.value = 0;
    }

    // Assignment operator
    MyClass& operator=(const MyClass& other) {
        if (this != &other) value = other.value;
        return *this;
    }

    ~MyClass() {  // destructor — object destroy hone pe call hota hai
        cout << "Destroyed!\n";
    }
};
```

**Rule of Five:** Agar ek define karo (destructor/copy constructor/copy assign/move constructor/move assign), toh sab define karo.

---

### Inheritance

```cpp
class Animal {  // Base class
public:
    string name;
    Animal(string n) : name(n) {}

    virtual void sound() {  // virtual — override ke liye
        cout << name << " makes a sound\n";
    }

    virtual ~Animal() {}  // virtual destructor — zaroori hai!
};

class Dog : public Animal {  // Derived class
public:
    Dog(string n) : Animal(n) {}

    void sound() override {  // override — C++11
        cout << name << " barks: Woof!\n";
    }
};

class Cat : public Animal {
public:
    Cat(string n) : Animal(n) {}

    void sound() override {
        cout << name << " meows: Meow!\n";
    }
};

int main() {
    Animal* a1 = new Dog("Buddy");
    Animal* a2 = new Cat("Whiskers");

    a1->sound();  // Buddy barks: Woof!
    a2->sound();  // Whiskers meows: Meow!

    delete a1;
    delete a2;
}
```

**Inheritance Types:**
```cpp
class D : public B {};     // public: public/protected sab maintain
class D : protected B {};  // protected: public → protected
class D : private B {};    // private: sab private (default for class)
```

---

### Abstract Classes & Pure Virtual Functions

```cpp
class Shape {  // Abstract class
public:
    virtual double area() = 0;      // pure virtual — must override
    virtual double perimeter() = 0; // pure virtual

    virtual ~Shape() {}
};

class Circle : public Shape {
    double radius;
public:
    Circle(double r) : radius(r) {}
    double area() override { return 3.14159 * radius * radius; }
    double perimeter() override { return 2 * 3.14159 * radius; }
};

// Shape s; // ERROR — abstract class ka object nahi ban sakta
Shape* s = new Circle(5.0);
cout << s->area();  // 78.5...
delete s;
```

---

### Operator Overloading

```cpp
class Vector2D {
public:
    double x, y;
    Vector2D(double x, double y) : x(x), y(y) {}

    // + operator overload
    Vector2D operator+(const Vector2D& other) const {
        return Vector2D(x + other.x, y + other.y);
    }

    // << operator overload (friend function)
    friend ostream& operator<<(ostream& os, const Vector2D& v) {
        os << "(" << v.x << ", " << v.y << ")";
        return os;
    }

    // == operator
    bool operator==(const Vector2D& other) const {
        return x == other.x && y == other.y;
    }
};

int main() {
    Vector2D v1(1, 2), v2(3, 4);
    Vector2D v3 = v1 + v2;
    cout << v3;  // (4, 6)
}
```

---

### `static` Members

```cpp
class Counter {
public:
    static int count;  // shared by all objects
    Counter() { count++; }
    ~Counter() { count--; }
    static int getCount() { return count; }
};

int Counter::count = 0;  // definition outside class

int main() {
    Counter c1, c2, c3;
    cout << Counter::count;      // 3
    cout << Counter::getCount(); // 3
}
```

---

### `friend` Function & Class

```cpp
class Box {
    double width;
public:
    Box(double w) : width(w) {}
    friend double getWidth(Box b);  // friend function declaration
    friend class BoxHelper;         // friend class
};

double getWidth(Box b) {
    return b.width;  // private member access kar sakta hai
}
```

---

## SECTION 12 — Templates

### Function Templates

```cpp
template <typename T>
T maximum(T a, T b) {
    return (a > b) ? a : b;
}

cout << maximum(3, 7);      // int version
cout << maximum(3.14, 2.7); // double version
cout << maximum('a', 'z');  // char version

// Multiple type parameters
template <typename T, typename U>
auto add(T a, U b) -> decltype(a + b) {
    return a + b;
}
```

---

### Class Templates

```cpp
template <typename T>
class Stack {
private:
    vector<T> data;
public:
    void push(const T& item) { data.push_back(item); }
    void pop() { data.pop_back(); }
    T& top() { return data.back(); }
    bool empty() const { return data.empty(); }
    int size() const { return data.size(); }
};

Stack<int> intStack;
intStack.push(1);
intStack.push(2);
cout << intStack.top();  // 2

Stack<string> strStack;
strStack.push("Hello");
```

---

### Template Specialization

```cpp
// General template
template <typename T>
void print(T val) {
    cout << "Value: " << val << endl;
}

// Specialization for bool
template <>
void print<bool>(bool val) {
    cout << "Bool: " << (val ? "true" : "false") << endl;
}

print(42);      // Value: 42
print(true);    // Bool: true
```

---

### Variadic Templates (C++11)

```cpp
template <typename T>
void printAll(T t) {
    cout << t << endl;
}

template <typename T, typename... Args>
void printAll(T t, Args... args) {
    cout << t << " ";
    printAll(args...);  // recursive
}

printAll(1, 2.5, "hello", 'A');  // 1 2.5 hello A
```

---

## SECTION 13 — Standard Template Library (STL)

### STL Components

```
STL = Containers + Iterators + Algorithms + Function Objects
```

---

### Sequence Containers

#### `vector`
```cpp
vector<int> v = {1, 2, 3};
v.push_back(4);
v.insert(v.begin(), 0);  // {0, 1, 2, 3, 4}
v.erase(v.begin() + 2);  // {0, 1, 3, 4}
sort(v.begin(), v.end());
```

#### `list` (Doubly Linked List)
```cpp
list<int> l = {1, 2, 3};
l.push_front(0);
l.push_back(4);
l.reverse();
l.sort();
l.remove(2);  // value 2 remove karo
```

#### `deque` (Double-Ended Queue)
```cpp
deque<int> dq = {1, 2, 3};
dq.push_front(0);
dq.push_back(4);
dq.pop_front();
dq.pop_back();
```

---

### Associative Containers

#### `map` (Sorted Key-Value)
```cpp
map<string, int> scores;
scores["Alice"] = 95;
scores["Bob"] = 87;
scores.insert({"Charlie", 91});

for (auto& [key, val] : scores) {  // structured binding C++17
    cout << key << ": " << val << "\n";
}

if (scores.count("Alice")) cout << "Found!";
scores.erase("Bob");
```

#### `unordered_map` (Hash Map — Faster Lookup)
```cpp
unordered_map<string, int> um;
um["key"] = 42;
cout << um["key"];  // 42
cout << um.count("key");  // 1 or 0
```

#### `set` (Unique Sorted Elements)
```cpp
set<int> s = {3, 1, 4, 1, 5, 9};
// s = {1, 3, 4, 5, 9} — duplicates removed, sorted
s.insert(2);
s.erase(4);
if (s.count(3)) cout << "Found 3!";
```

---

### Container Adaptors

#### `stack` (LIFO)
```cpp
stack<int> stk;
stk.push(1); stk.push(2); stk.push(3);
cout << stk.top();  // 3
stk.pop();
cout << stk.size(); // 2
```

#### `queue` (FIFO)
```cpp
queue<int> q;
q.push(1); q.push(2); q.push(3);
cout << q.front(); // 1
cout << q.back();  // 3
q.pop();
```

#### `priority_queue` (Max-Heap by default)
```cpp
priority_queue<int> pq;  // max-heap
pq.push(3); pq.push(1); pq.push(4);
cout << pq.top();  // 4 (largest)
pq.pop();

// Min-heap
priority_queue<int, vector<int>, greater<int>> minPq;
```

---

### Iterators

```cpp
vector<int> v = {1, 2, 3, 4, 5};

// begin/end
vector<int>::iterator it = v.begin();
cout << *it;  // 1
++it;
cout << *it;  // 2

// auto se simpler
for (auto it = v.begin(); it != v.end(); ++it) {
    cout << *it << " ";
}

// Reverse iterators
for (auto it = v.rbegin(); it != v.rend(); ++it) {
    cout << *it << " ";  // 5 4 3 2 1
}

// Iterator arithmetic (only random access iterators)
auto it2 = v.begin() + 3;
cout << *it2;  // 4
```

---

### Common Algorithms (`<algorithm>`)

```cpp
vector<int> v = {3, 1, 4, 1, 5, 9, 2, 6};

sort(v.begin(), v.end());               // ascending sort
sort(v.begin(), v.end(), greater<int>()); // descending
stable_sort(v.begin(), v.end());        // stable sort

auto it = find(v.begin(), v.end(), 5);  // linear search
if (it != v.end()) cout << "Found: " << *it;

auto it2 = lower_bound(v.begin(), v.end(), 4); // binary search (sorted)
auto it3 = upper_bound(v.begin(), v.end(), 4);

int cnt = count(v.begin(), v.end(), 1);  // count occurrences

int mx = *max_element(v.begin(), v.end());
int mn = *min_element(v.begin(), v.end());

reverse(v.begin(), v.end());

// Check conditions
bool allPos = all_of(v.begin(), v.end(), [](int x) { return x > 0; });
bool anyNeg = any_of(v.begin(), v.end(), [](int x) { return x < 0; });
bool noneNeg = none_of(v.begin(), v.end(), [](int x) { return x < 0; });

// Transform
transform(v.begin(), v.end(), v.begin(), [](int x) { return x * 2; });

// Fill
fill(v.begin(), v.end(), 0);

// Copy
vector<int> dest(v.size());
copy(v.begin(), v.end(), dest.begin());

// Remove (logical remove — erase-remove idiom)
v.erase(remove(v.begin(), v.end(), 1), v.end());

// Unique (sorted mein se duplicates remove)
v.erase(unique(v.begin(), v.end()), v.end());

// Accumulate
#include <numeric>
int sum = accumulate(v.begin(), v.end(), 0);
```

---

## SECTION 14 — Exception Handling

**Definition:** Exception handling errors ko gracefully handle karne ki mechanism hai.

```cpp
try {
    // code jo exception throw kar sakta hai
    int a = 10, b = 0;
    if (b == 0) throw runtime_error("Division by zero!");
    cout << a / b;

} catch (const runtime_error& e) {
    cout << "Error: " << e.what() << endl;

} catch (const exception& e) {  // base class — sab exceptions catch
    cout << "Exception: " << e.what() << endl;

} catch (...) {  // any exception — last resort
    cout << "Unknown exception!\n";
}
```

---

### Standard Exceptions

```cpp
#include <stdexcept>

throw runtime_error("runtime problem");
throw logic_error("logic problem");
throw out_of_range("index out of range");
throw invalid_argument("invalid argument");
throw overflow_error("overflow");
throw underflow_error("underflow");
throw bad_alloc();  // new fail hone pe automatically throw hota hai
```

---

### Custom Exceptions

```cpp
class MyException : public exception {
    string message;
public:
    MyException(const string& msg) : message(msg) {}
    const char* what() const noexcept override {
        return message.c_str();
    }
};

try {
    throw MyException("Custom error occurred!");
} catch (const MyException& e) {
    cout << e.what() << endl;
}
```

---

### `noexcept` Specifier (C++11)

```cpp
void safeFunction() noexcept {
    // koi exception throw nahi karega
}

// Conditional noexcept
template <typename T>
void f(T t) noexcept(noexcept(t.method())) {
    t.method();
}
```

---

## SECTION 15 — File I/O

### File Operations

```cpp
#include <fstream>

// Writing to file
ofstream outFile("output.txt");
if (outFile.is_open()) {
    outFile << "Hello, File!\n";
    outFile << 42 << "\n";
    outFile.close();
}

// Reading from file
ifstream inFile("output.txt");
string line;
while (getline(inFile, line)) {
    cout << line << "\n";
}
inFile.close();

// Read/Write (fstream)
fstream file("data.txt", ios::in | ios::out | ios::app);

// File open modes
ios::in    // read
ios::out   // write
ios::app   // append (end mein add)
ios::ate   // file end pe jaao
ios::trunc // file khali karo
ios::binary // binary mode
```

---

### Binary File I/O

```cpp
struct Person {
    char name[50];
    int age;
};

// Write binary
Person p = {"Rahul", 25};
ofstream out("person.bin", ios::binary);
out.write(reinterpret_cast<char*>(&p), sizeof(p));
out.close();

// Read binary
Person p2;
ifstream in("person.bin", ios::binary);
in.read(reinterpret_cast<char*>(&p2), sizeof(p2));
cout << p2.name << " " << p2.age;  // Rahul 25
in.close();
```

---

### String Streams

```cpp
#include <sstream>

// String se read (input)
string data = "Rahul 25 9.5";
istringstream iss(data);
string name;
int age;
double gpa;
iss >> name >> age >> gpa;

// String mein write (output)
ostringstream oss;
oss << "Name: " << name << ", Age: " << age;
string result = oss.str();

// Both (stringstream)
stringstream ss;
ss << 42;
int n;
ss >> n;
```

---

## SECTION 16 — Modern C++ (C++11/14/17/20 Features)

### C++11 Key Features

#### Move Semantics
```cpp
// Lvalue: naam hai, address hai
// Rvalue: temporary, naam nahi, jaise 42, x+y

void process(vector<int>&& v) {  // rvalue reference
    // v ko move kar sakte hain
}

vector<int> v1 = {1, 2, 3};
vector<int> v2 = move(v1);  // v1 se resources transfer, copy nahi
// v1 ab empty hai
```

#### `nullptr`
```cpp
int* p = nullptr;  // NULL se better — type-safe
```

#### `initializer_list`
```cpp
#include <initializer_list>

void printAll(initializer_list<int> list) {
    for (int x : list) cout << x << " ";
}
printAll({1, 2, 3, 4, 5});
```

#### Enum Class (Scoped Enum)
```cpp
enum class Color { Red, Green, Blue };  // scoped
Color c = Color::Red;  // prefix zaroori hai

// Old enum
enum Direction { North, South, East, West };  // unscoped
Direction d = North;  // prefix nahi chahiye
```

---

### C++11 Type Aliases

```cpp
using IntPtr = int*;           // alias
using StringMap = map<string, string>;

typedef int* IntPtr2;          // old style
```

---

### C++11/14 `constexpr`

```cpp
constexpr int factorial(int n) {
    return (n <= 1) ? 1 : n * factorial(n - 1);
}

constexpr int val = factorial(5);  // compile time pe calculate! = 120
```

---

### C++17 Structured Bindings

```cpp
// pair decompose karo
pair<int, string> p = {1, "hello"};
auto [id, name] = p;
cout << id << " " << name;

// map iterate karo
map<string, int> m = {{"a", 1}, {"b", 2}};
for (auto& [key, value] : m) {
    cout << key << ": " << value << "\n";
}
```

---

### C++17 `if` with Initializer

```cpp
if (auto it = m.find("key"); it != m.end()) {
    cout << it->second;  // it scope sirf if block mein hai
}
```

---

### C++17 `std::optional`

```cpp
#include <optional>

optional<int> divide(int a, int b) {
    if (b == 0) return nullopt;
    return a / b;
}

auto result = divide(10, 2);
if (result.has_value()) cout << result.value();  // 5
if (result) cout << *result;                      // same

auto r2 = divide(10, 0);
cout << r2.value_or(-1);  // -1 (default value)
```

---

### C++17 `std::variant`

```cpp
#include <variant>

variant<int, double, string> v;
v = 42;
cout << get<int>(v);  // 42

v = 3.14;
cout << get<double>(v);  // 3.14

v = "hello";
cout << get<string>(v);  // hello

// Safe access
if (holds_alternative<int>(v)) {
    cout << get<int>(v);
}
```

---

### C++20 Concepts

```cpp
#include <concepts>

template <typename T>
concept Numeric = requires(T a, T b) {
    { a + b } -> convertible_to<T>;
    { a - b } -> convertible_to<T>;
};

template <Numeric T>
T add(T a, T b) { return a + b; }

// Shorthand
auto multiply(auto a, auto b) requires Numeric<decltype(a)> {
    return a * b;
}
```

---

### `std::string_view` (C++17)

```cpp
#include <string_view>

// String ka view — copy nahi, efficient
void print(string_view sv) {
    cout << sv << "\n";
}

string s = "Hello, World!";
print(s);           // string
print("Literal");   // string literal — no copy!
print({s.data(), 5}); // substring view
```

---

### Ranges (C++20)

```cpp
#include <ranges>

vector<int> v = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

// Filter + transform pipeline
auto result = v
    | views::filter([](int x) { return x % 2 == 0; })
    | views::transform([](int x) { return x * x; });

for (int x : result) cout << x << " ";  // 4 16 36 64 100
```

---

## QUICK REFERENCE — Common Patterns

### Singleton Pattern
```cpp
class Singleton {
    Singleton() {}
    static Singleton* instance;
public:
    static Singleton* getInstance() {
        if (!instance) instance = new Singleton();
        return instance;
    }
};
Singleton* Singleton::instance = nullptr;
```

### RAII Pattern (Resource Acquisition Is Initialization)
```cpp
class FileWrapper {
    FILE* fp;
public:
    FileWrapper(const char* name) { fp = fopen(name, "r"); }
    ~FileWrapper() { if (fp) fclose(fp); }  // automatic cleanup
    FILE* get() { return fp; }
};
```

### Copy-and-Swap Idiom
```cpp
class MyClass {
    int* data;
    int size;
public:
    friend void swap(MyClass& a, MyClass& b) noexcept {
        using std::swap;
        swap(a.data, b.data);
        swap(a.size, b.size);
    }

    MyClass& operator=(MyClass other) {  // pass by value
        swap(*this, other);
        return *this;
    }
};
```

---

## COMMON INTERVIEW QUESTIONS

| Topic | Key Points |
|-------|-----------|
| Virtual vs Pure Virtual | Virtual = default implementation, Pure = `= 0`, abstract class |
| `new` vs `malloc` | `new` = constructor call + type-safe; `malloc` = C, no constructor |
| `delete` vs `free` | `delete` = destructor call; `free` = C, no destructor |
| `struct` vs `class` | Default access: struct = public, class = private |
| `stack` vs `heap` | Stack = automatic, fast, limited; Heap = manual, slow, large |
| `const` vs `constexpr` | const = runtime const; constexpr = compile-time const |
| `override` vs `virtual` | virtual = can override; override = C++11 keyword to explicitly override |
| Reference vs Pointer | Ref = alias, no null, no reassign; Ptr = address, nullable, reassignable |
| Shallow vs Deep Copy | Shallow = pointer copy; Deep = new memory allocation |
| Compilation stages | Preprocessor → Compiler → Assembler → Linker |

---

## COMPLEXITY CHEAT SHEET

| Container/Operation | Average | Worst |
|--------------------|---------|-------|
| `vector` access | O(1) | O(1) |
| `vector` insert/delete end | O(1) | O(n) |
| `vector` insert/delete middle | O(n) | O(n) |
| `list` insert/delete | O(1) | O(1) |
| `map` access/insert/delete | O(log n) | O(log n) |
| `unordered_map` access/insert | O(1) | O(n) |
| `set` insert/find | O(log n) | O(log n) |
| `sort` | O(n log n) | O(n log n) |
| `binary_search` | O(log n) | O(log n) |
| `linear search (find)` | O(n) | O(n) |

---

*Made with ❤️ for C++ learners — Beginner se Pro tak! 🚀*
