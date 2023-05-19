---
marp: true
author: Christine Okoth
theme: uncover
---

# Dynamic Memory Allocation in C: `malloc` and `free`

---

## Understanding Memory Allocation

### Why do we need to allocate memory?

In C programming, memory allocation is essential for tasks such as:

- Storing data structures dynamically, where the size is determined at runtime.
- Avoiding fixed-size limitations.
- Efficient use of memory resources.

---

### What is the `malloc` function?

- `malloc` (short for "memory allocation") is a function in C that dynamically allocates memory at runtime.
- It is defined in the `stdlib.h` header file.

---

### How does the `malloc` function work?

The `malloc` function works as follows:

1. It takes the number of bytes as an argument and returns a pointer to the allocated memory block.
2. If the memory allocation is successful, `malloc` reserves a contiguous block of memory of the specified size.
3. If the allocation fails (insufficient memory), `malloc` returns a `NULL` pointer.

---

### What is the `free` function?

- `free` is a function in C used to release dynamically allocated memory.
- It is defined in the `stdlib.h` header file.

---

### How does the `free` function work?

The `free` function works as follows:

1. It takes a pointer to the memory block to be freed as an argument.
2. The memory block, previously allocated using `malloc`, is deallocated and made available for reuse.
3. After calling `free`, the pointer should not be used anymore, as the memory is no longer valid.

---

### Example Usage

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int size = 5;
    int* dynamicArray = (int*)malloc(size * sizeof(int));

    if (dynamicArray == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Access and modify elements of the dynamically allocated array
    for (int i = 0; i < size; i++) {
        dynamicArray[i] = i + 1;
    }

    // Print the elements of the dynamically allocated array
    for (int i = 0; i < size; i++) {
        printf("%d ", dynamicArray[i]);
    }

    printf("\n");

    // Free the dynamically allocated memory
    free(dynamicArray);

    return 0;
}
```
