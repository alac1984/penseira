15/01/2023 15:06

Tags: [[C]] [[Computer Science]]

In C programming language, a string literal is a sequence of characters that are stored in contiguous memory, terminated by a null character ("\\0"). For example,

| E | a | r | t | h | \\0 |
| - | - | - | - | - | - |

is a 6 byte string.

When we pass a string to a function like below:

```c
printf("Welcome to my channel!")
```

We are not passing the full string to the function. Instead, we're passing just a pointer to the first character. Passing `"Welcome to my channel"` is the same thing as passing the pointer for the letter `"W"`.

Both `printf` and `scanf` functions expect a character pointer ( `char*`) as an argument.

---
# References

