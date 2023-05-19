---
marp: true
author: Christine Okoth
theme: uncover
---

# Lets Learn about Pointers!!

![pointers](https://1.bp.blogspot.com/-FaClhEEH0HU/XwW1a9OoyGI/AAAAAAAAAY0/b8rxxCvTzeIqGJ5RDWjlo-1c38z0nnasgCK4BGAsYHg/w1600/pointers.jpg)

---

## What is a pointer?

- a pointer is a variable that stores the memory address of another variable.

- When you create a variable in C, it is assigned a memory address in your computer's memory.
  - This memory address is a unique identifier for that variable.

---

Lets break that down;

- To assign a value to a variable you simply declare the variable and give it a value. eg;

```perl
int x = 5;
```

- Here, you have defined a variable x and given it a value.

---

- To acces the value, you simple use the variable name.
  - Like this;

```perl
printf("%d", x);
```

- In this case, the value of the variable x (5) is printed to the console.

---

- However, this doesn't give you x's value address. What happens if you wanted to access the address?

- That's where pointers come in!
- A pointer will point to the memory address of x.

---

Here is what I mean;

```perl
int x = 5;
int *ptr = &x;
```

- In this case, the pointer variable "ptr" stores the memory address of the variable "x".

---

- You can access the value of x indirectly through the pointer variable, like this:

```perl
int value = *ptr;
printf("%d", value);
```

- The "\*" symbol in front of the pointer variable "ptr" is called the "dereference operator", and it is used to access the value stored at the memory address pointed to by the pointer.

---

# Pointers and Strings

- A string is an array of characters.

eg;

hello = 'h', 'e', 'l', 'l', 'o'

- When a pointer is used to point to a string in C, it works by storing the memory address of the first character of the string.

---

For example, you can declare a string variable like this:

```C
Char str[] = "Hello";
```

- This assigns the memory a sequence of characters. from 'H' to 'o' followed by a null terminator '\0'.
- The null terminator simply indicates the end of the string.

---

- You can then declare a pointer variable to point to the first character of this string:

```C
char *ptr = str;
```

- The value of the pointer variable will be the memory address of the first character of the string (i.e., the 'H' in "Hello").

---

- Now, you can use the pointer variable to access and modify the characters in the string. For example:

```C
/*Print the first character of the string using the pointer*/
printf("%c", *ptr);
```

- Here, the printf statement uses the dereference operator \* to access the value stored at the memory location pointed to by "ptr", which is the first character of the string.

---

```C
/*Modify the second character of the string using the pointer*/
(ptr + 1) = 'a';
```

- This second statement modifies the second character of the string using pointer arithmetic.
- The expression "ptr + 1" calculates the memory address of the second character of the string (i.e., the 'e' in "Hello"), and the dereference operator \* is used to access the value stored at that memory location.
- By assigning the value 'a' to this location, we modify the second character of the string to be "Hallo".

---

```C
/*Print the modified string using the original variable*/
printf("%s", str);
```

- Finally, the third printf statement prints the modified string by passing the original variable "str" to the printf function.

---

## Importance of Pointers

#### Memory Efficiency

Pointers help us use our computer's memory in a smart way. Think of memory as small containers where we store information. With pointers, we can create and use containers of different sizes as we need them. It's like having a magic bag that can change its size depending on how much stuff we want to put in it. This way, we don't waste memory or run out of space.

---

#### Passing Data by Reference:

Normally, when we want to share information with someone, we make copies of it. But making copies can take a lot of time and memory, especially for big things. Pointers help us avoid making copies. Instead, we can give someone the address of the information we want to share. It's like giving them a map to find the original information. This saves time and memory because we don't need to make extra copies.

---

#### Working with Complex Data Structures:

Sometimes we need to organize information in special ways, like building a tower with blocks or connecting dots with lines. Pointers help us do that. They are like arrows that point to other pieces of information. With these arrows, we can create complex structures like puzzles, where each piece knows where to find the next one. This makes it easy to move around and work with lots of information without getting confused.

---

#### Interfacing with Hardware:

Computers have special parts called hardware that help them do specific tasks. Sometimes we need to talk directly to these parts to make them do what we want. Pointers are like magic wands that let us touch these special parts and tell them what to do. It's like having a secret code to control the computer's hardware and make it work just the way we need it to.

---

##### Conclusion

So, pointers are like special tools that help us use memory efficiently, share information without making copies, create complex structures, and talk to the computer's special parts. They make programming more powerful and give us lots of possibilities to solve problems and create amazing things with computers.
