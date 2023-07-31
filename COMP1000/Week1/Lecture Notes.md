C is 51 years old but fucking fast (if done correctly), it is not Object Oriented 

There is an EXAM ;-; bullshit if you ask me

using GCC to compile in this unit, 
`-Wall` Show all warnings W(arnings)all
`-ansi` Tells the compiler to implement the ANSI language option. This turns off certain "features" of GCC which are incompatible with the ANSI standard.
`-pedantic` Used in conjunction with `-ansi`, this tells the compiler to be adhere strictly to the ANSI standard, rejecting any code which is not compliant.

**Pointer, Pointer, Pointer** - Pointers will be discussed in lecture 3, it is the heat and soul of C, you MUST understand pointers.

Week 3 and 6 will be difficult but others should be fine.

# Likely Data types:
---
*Signed integers* - int, short, long
*Unsigned (not -ve) integers* - unsigned int, unsigned short, unsigned long
*Reals* - float, double (2x float size), long double (little bit bigger)
*Characters* - char (single letter, digit, symbol, etc)

# For Loops:
---
```c
int i;

for(i=0, i <=10, i++){
	/* Do thing */
}
```
Initialise your increment variable outside the loop, 
the for loop takes in 3 arguments ICE - "initial", "condition", "edit"

# Comments: 
---
you can ONLY comment with `/*  */`

# Jump Statements:
---
`Return`- at the end of a function output the arguments and end the function
`Break` - Will immediately end the current statement (Switch, For, While, or do-while). ONLY USE FOR SWITCH, its nicer and for the unit you are not allowed to use for anything else
`Continue` - Ends the current iteration of a loop, continues the loop after. DO NOT USE IN THIS UNIT
`goto` - A relic from the dark ages, will take you to any line in your code. NEVER USE EVER, bad habits, poor programming, terrible terrible structure, breaks rules. 

# Functions:
---
A chunk of code that you can recall at any point within your main function. They must remain separate, you cannot declare a function within a function.
```c
int Multiplication(int x, int y){
	return x * y;
}
```

```c
void printHello(){ /*intends to return nothing*/
	printf("hello");
}

void printHello(void){ /*you CANNOT input any arguments*/
	printf("hello");
}
```

# Outputting data - printf():
---
```c
printf("output", variable);
```
`stdio` library required (standard in out)
the arguments required is a "string" (obviously no strings in C89 natively)

if you want to input a variable use a place holder of the right data type
`%d` integer
`%f` float
`%c` character
`%s` array of characters

# Inputting data - scanf():
---
```c
scanf("input", address) /*ie. %d as the input*/
```
the scanf function will take input data from the console and send it to an address (`&`) 

# Forward Declarations:
---
Code must be declared (written) "in order", you can only "use" a function if it has already been declared. This is because C is complied in a single pass, from top to bottom, so if a function is implemented prior to declaration the compiler will be unable to know the function exists.
This is easily solvable by declaring the function above its use, or in another file (to be covered in week 2)