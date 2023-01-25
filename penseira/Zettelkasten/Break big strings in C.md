15/01/2023 14:56

Tags: [[C]]

To break big string in C, you have to separate them using double quotes like this:

```c
printf("%s", "You have to dream before you dreams can come true. "
	"-- A.P.J. Abdul Kalam")
```

If you use backslash as below

```c
printf("%s", "You have to dream before you dreams can come true. \
	-- A.P.J. Abdul Kalam")
```

the indentation spaces will appear in the output, like this:

```stdout

>> "You have to dream before you dreams can come true.     -- A.P.J. Abdul Kalam")
```

---
# References

https://www.youtube.com/watch?v=IlqiTmcK1Eg&list=PLBlnK6fEyqRhwQbYrTDZYJaB4z1YgsAPW&index=1 