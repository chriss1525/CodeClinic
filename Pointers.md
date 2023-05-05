# Lets Learn about Pointers!!

## What is a pointer?

a pointer is a variable that stores the memory address of another variable.

When you create a variable in C, it is assigned a memory address in your computer's memory. This memory address is a unique identifier for that variable. eg;

```perl
int x = 5;
```

in this example, you have defined a variable x and given it a value. To acces the value, you simple use the variable name. Like this;

```perl
printf("%d", x);
```

In this case, the value of the variable x (which is 5) is printed to the console.

However, this doesn't give you x's value address. What happens if you wanted to access the address?

That's where pointers come in! A pointer will point to the memory address of x and not to the value of x.

Here is what I mean;

```perl
int x = 5;
int *ptr = &x;
```

In this case, the pointer variable "ptr" stores the memory address of the variable "x". You can access the value of x indirectly through the pointer variable, like this:

```perl
int value = *ptr;
printf("%d", value);
```

The "\*" symbol in front of the pointer variable "ptr" is called the "dereference operator", and it is used to access the value stored at the memory address pointed to by the pointer.

# Pointers and Strings

A string is an array of characters.

eg;

> hello = 'h', 'e', 'l', 'l', 'o'

When a pointer is used to point to a string in C, it works by storing the memory address of the first character of the string.

For example, if you declare a string variable like this:

```C
Char str[] = "Hello";
```

This assigns the memory a sequence of characters. from 'H' to 'o' followed by a null terminator '\0'. The null terminator simply indicates the end of the string.

If you declare a pointer variable to point to the first character of this string:

```C
char *ptr = str;
```

Then the value of the pointer variable will be the memory address of the first character of the string (i.e., the 'H' in "Hello").

Now, you can use the pointer variable to access and modify the characters in the string. For example:

```C
/*Print the first character of the string using the pointer*/
printf("%c", *ptr);
```

In this example, the printf statement uses the dereference operator \* to access the value stored at the memory location pointed to by "ptr", which is the first character of the string.

```C
/_Modify the second character of the string using the pointer_/
\*(ptr + 1) = 'a';
```

This second statement modifies the second character of the string using pointer arithmetic. The expression "ptr + 1" calculates the memory address of the second character of the string (i.e., the 'e' in "Hello"), and the dereference operator \* is used to access the value stored at that memory location. By assigning the value 'a' to this location, we modify the second character of the string to be "Hallo".

```C
/_Print the modified string using the original variable_/
printf("%s", str);
```

Finally, the third printf statement prints the modified string by passing the original variable "str" to the printf function.
