# Challenge:
---
Calculator with multiple inputs (>2) if desired.
Take in integer from the user and handle non-numerical inputs
test Must work with multiple numbers in succession 
*Find on my GitHub*

## Fun code (I think its optimal, but what would I know):
---
```c
#include <stdio.h>
#include <stdlib.h>

int factorial(int n) {
    int i;

    int factorial(int n) { 
		if (n <= 1) return 1; 
	else return n * factorial(n - 1); }
}

int main() {

    int inputNumber;

    restart:;

    printf("Input Number of Factorials:");
    scanf("%d", &inputNumber);
    if(inputNumber >= 0){
        printf("%d \n",factorial(inputNumber));
        goto restart;
    }

    return 0;
}
```

