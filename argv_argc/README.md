---
marp: true
author: Christine Okoth
theme: uncover
---

# Command Line Arguments in C: `argv` and `argc`

---

## Understanding `argv` and `argc`

### What are `argv` and `argc`?

- `argv` (argument vector) is an array of strings that holds the command line arguments passed to the program.
- `argc` (argument count) is an integer that represents the number of command line arguments passed to the program, including the program name itself.

---

### Why use Command Line Arguments?

Command line arguments provide a way to pass data to a program when executing it from the command line. They allow for:

- Flexibility: The behavior of the program can be altered without modifying the source code.
- Input Data: Input values or configuration parameters can be provided to the program during runtime.
- Automation: Scripts or other programs can invoke programs with specific arguments.

---

### How to Access Command Line Arguments

In C, the `main` function has two parameters: `argc` and `argv`. You can access the command line arguments using these parameters:

```c
int main(int argc, char* argv[]) {
    // Code to process command line arguments
    return 0;
}
```

---

## Example Usage

Let's consider an example where a program expects two command line arguments: name and age:

```C
#include <stdio.h>

int main(int argc, char* argv[]) {
    if (argc != 3) {
        printf("Usage: %s <name> <age>\n", argv[0]);
        return 1;
    }

    char* name = argv[1];
    int age = atoi(argv[2]);

    printf("Hello, %s! Your age is %d.\n", name, age);

    return 0;
}
```

---

In this example, the program checks if the number of arguments (argc) is equal to 3. If not, it displays the correct usage to the user.

If the correct number of arguments is provided, the program assigns the values to name and age variables using argv[1] and argv[2], respectively. It then prints a personalized message using these values.

---

# Conclusion

- Command line arguments (argv and argc) in C provide a convenient way to pass data and customize the behavior of a program from the command line. 
- By understanding how to use them, you can create more flexible and interactive programs.

---

- Feel free to explore the examples and explanations provided in this repository. Modify and experiment with the code to deepen your understanding of command line arguments in C.

- If you have any questions or need further assistance, feel free to reach out.

---

> Happy coding!
