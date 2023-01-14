14/01/2023 17:27

Status: #information

Tags: [[C]]

If you write a code like this:

```c
#include <stdio.h>

int main(void) {
	for(int i = 0, i < 3, i++) {
		meow();	
	}
}

void meow(void) {
	printf("meow")
}
```

You'll get a `implicit declaration` error, as C compiler will not find the `meow` function at the time it read the foor loop insides. The way to fix this is by writing

```c
#include <stdio.h>

void meow(void); // put this

int main(void) {
	for(int i = 0, i < 3, i++) {
		meow();	
	}
}

void meow(void) {
	printf("meow")
}
```

That  way C compiler will find the function definition before it hit the for loop insides. That "declaration" of the function at the top is called a "prototype".

---
# References

EDX CS50 Harvard Course:
https://video.cs50.io/URrzmoIyqLw?screen=jHZVEq21njk&start=6601

Stack Overflow about Prototypes:
https://stackoverflow.com/questions/23661729/what-are-prototypes-in-a-c-program