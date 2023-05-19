---
marp: true
author: Christine Okoth
theme: uncover
---

## Recursion

![Recursion](https://pencilprogrammer.com/wp-content/uploads/2018/11/Recursion-in-C-min.png)

---

### What is Recursion?

Recursion is a programming concept where a function calls itself to solve a problem. It breaks down a problem into smaller, similar subproblems until a base case is reached.

---

### Why Recursion?

- **Simplicity**: Recursion provides an elegant and intuitive solution to certain problems.
- **Divide and Conquer**: Recursion follows the "divide and conquer" approach, solving smaller subproblems to solve the entire problem.
- **Solving Recursive Problems**: Some problems are inherently recursive in nature and can be solved more efficiently using recursion.

---

### How to Use Recursive Functions

To use recursion:

1. Define the base case: The simplest version of the problem that can be solved directly.
2. Define the recursive case: Break down the problem into smaller subproblems.
3. Invoke the function: Call the function itself with modified inputs to solve the subproblems.
4. Combine the results: Combine the results from the recursive calls, if needed.

---

### Examples of Recursive Functions

- Factorial calculation: Calculates the factorial of a number recursively.

```C
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

result = factorial(5)
print(result)  # Output: 120

```

---

- Fibonacci sequence: Generates the nth number in the Fibonacci sequence using recursion.

```C
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

result = fibonacci(6)
print(result)  # Output: 8

```

---

## Pointers

### Traversing Pointers with recursive functions

#### Pointers to Strings

```C
#include <stdio.h>

void traverseString(char* str) {
    if (*str == '\0') {
        return;  // Base case: Reached the end of the string
    }

    putchar(*str);  // Print the current character
    traverseString(str + 1);  // Move to the next character recursively
}

int main() {
    char* myString = "Hello, World!";
    traverseString(myString);  // Output: Hello, World!

    return 0;
}
```

---

#### Pointers to Integers with recursive functions

```C
#include <stdio.h>

void traverseIntegers(int* arr, int size) {
    if (size == 0) {
        return;  // Base case: No more elements in the array
    }

    printf("%d ", *arr);  // Print the current integer
    traverseIntegers(arr + 1, size - 1);  // Move to the next integer recursively
}

int main() {
    int myArray[] = {1, 2, 3, 4, 5};
    int size = sizeof(myArray) / sizeof(myArray[0]);
    traverseIntegers(myArray, size);  // Output: 1 2 3 4 5

    return 0;
}
```

---

#### Pointers to Arrays and recursive functions

```C
#include <stdio.h>

void traverseArrays(int (*arr)[3], int rows, int cols) {
    if (rows == 0) {
        return;  // Base case: No more rows in the array
    }

    for (int i = 0; i < cols; i++) {
        printf("%d ", (*arr)[i]);  // Print the current element
    }

    printf("\n");
    traverseArrays(arr + 1, rows - 1, cols);  // Move to the next row recursively
}

int main() {
    int myArray[][3] = {{1, 2, 3},
                        {4, 5, 6},
                        {7, 8, 9}};
    int rows = sizeof(myArray) / sizeof(myArray[0]);
    int cols = sizeof(myArray[0]) / sizeof(myArray[0][0]);
    traverseArrays(myArray, rows, cols);  // Output: 1 2 3 \n 4 5 6 \n 7 8 9 \n

    return 0;
}
```

---

## Recursion vs. Loops

Recursion and loops are two different approaches to problem-solving:

- Recursion involves a function calling itself, breaking down problems into smaller subproblems.
- Loops use iterations to repeat a block of code until a condition is met.
- Recursion can be elegant and intuitive but may have higher memory usage compared to loops.

---

Feel free to explore the examples and explanations provided in this repository. You can run the code samples and experiment with them to deepen your understanding of recursion and pointers in programming.

If you have any questions or need further assistance, feel free to reach out.

---

> Happy coding!
