# CMPUT 201 Notes

## Disclaimer

This course by the U of A was taken during the 2020 quarantine and therefore may not be a true representation of a normal 201 class. People from previous years have claimed that topics such as dp (dynamic programming), greedy, graphs, and others were explored but Dr. Lin Guo-Hui did not really explore these topics. 

## General

This course is an intro to C. From pointers to make files, this course will develop an intuition for c programming (C++ is almost not taught, for C++ take 275). 



Course difficulty: Easy-medium

## Summary

### Week 1

Setting up up, ie, ssh into server, linux commands etc

```shell
# linux commands 
~ # home directory
mkdir cmput201 # make directory
cd cmput201 # change directory
mkdir Week01 # make dir called Week01
pwd # print working dir
ls ~ # list contents of home 
man ls # manual page of ls command
vi celsius.c # create a new or open an existing file in vi
```



Inline comments with `//` or `/* Some comments */` for block comments

Compiling with `gcc -Wall -std=c99`

**Recommended editor of vim or emacs on the school machine via ssh through Putty** but from my experience, WSL2 with vs code will have the same results as the school machines

### Week 2

printf and scanf

Escape sequences: ie `\n` for new line



int and float binary representation

- int - just dec to binary form
- float - converted via IEEE 754 standard



operators and precedence:

In order of highest priority to lowest (if on same level then left to right)

|                                  | associativity |
| -------------------------------- | ------------- |
| {postfix ++,−−}                  | right-to-left |
| {prefix ++,−−, unary +,−unary !} | right-to-left |
| {*, /, %}                        | left-to-right |
| {binary +,−}                     | left-to-right |
| {<, >, <=, >=}                   | left-to-right |
| {==, !=}                         | left-to-right |
| {&&,\|\|}                        | left-to-right |
| {assignment =, +=,−=, *=, /=, %= | right-to-left |

1D arrays, ie lists

```c
int a[10] = {1,2,3,4,5,6,7,8,9,10}; // stores the max 10 ints
int b[10] = {1,2,3,4,5,6,7,8*2}; 
int c[10] = {0}; // inits all elements in container c to 0
int e[] = {1, 2, 3, 4, 5, 6, 7}; // sets max automatically
int f[10] = {[2] = 2, [7] = 9, [9] = 7, [2] = 3};
```



Resources: 

https://www.tutorialspoint.com/c_standard_library/c_function_scanf.htm 

https://www.tutorialspoint.com/c_standard_library/c_function_printf.htm

https://www.geeksforgeeks.org/program-for-conversion-of-32-bits-single-precision-ieee-754-floating-point-representation/

### Week 3

for, while, do-while loops

comparison operators and conditional expressions (also not tertiary operators `expression ? true : false`)

No such thing as boolean only exists when including stdbool.h

### Week 4

Sorting algorithms 

#### Types in c

**sizes**

* int (signed) - 32bits/4bytes therefore largest is 2^32-1 or 2,147,483,647
* short - 16 bits
* long - 32/64 bits (system dependent)
* long long (often simplified to ll via definition) - 64 bits
* float - 32 bits
* double - 64 bits
* long double - 80 or 128 bits (mostly used for very high precision calculations like money or aeronautics)

`sizeof()` finds the size in bytes

**char**

* signed 128 ($2^7$) bits
* case sensitive
* signed integers of size 1 byte (8 bits)
* Stored as ASCII 
* *note all char must be expressed by single quotations ie `'w'`
* **Double quotations indicate a string type in c, therefore single vs double quotation marks matter**

**Changing Types**

To go from 1 type to another, one can apply as cast ie

```c
int a = 10;
float b = (float) a;
```

Another way types can change is via "**promoting**"

The compiler will always promote to the type with more storage

bool → char → short int → int → unsigned int → long int → unsigned long int( → )float → double → long double

**Floats**

Floats are represented with 

* 1 signed bit
* 8 exponent bits 
* 23 bits for binary representation (called fraction)

Class example

```
111:
-> in binary (base-2) system: 1101111
-> left filled w/ 0's: 0000000 00000000 00000000 01101111
-> add sign bit 0: 00000000 00000000 00000000 01101111

111.111:
-> integral part: 1101111
-> fractional part:
0.111 x2 = 0.222 -> 0
0.222 x2 = 0.444 -> 00
0.444 x2 = 0.888 -> 000
0.888 x2 = 1.776 -> 0001    0.776
0.776 x2 = 1.552 -> 00011   0.552
0.552 x2 = 1.104 -> 000111  0.104
0.104 x2 = 0.208 -> 0001110
0.208 x2 = 0.416 -> 00011100 ...

the exponential format (%a): 1.101111 00011100 ... x2^6
the exponent is 01111111 (= 127) + 6 (= 110) = 10000101
add sign bit 0: 0 10000101 101111 00011100 ...
```

**Type def**

```c
#define one 1
```

This is called a macro and will replace every instance of `one` with `1` literally. Think of this as a find and replace 

```c 
#typedef int Bool;
```

Bool is a new data type, and its type is int

**Multi-dimensional arrays**

instantiated with `int a[5][9]` and holds 5 rows with 9 columns

### Week 5

**Functions**

```c
# form
return-type function-name ( parameters ) {
    declarationsstatements
}
```

\* note returns value not an array

Use  keyword `static` to  declare the  minimum  length

ie `int sum(int a[static10][100], int n)`

* length is >= 10
* complier optimizes it

`exit()` (from `<stdlib.h>`) exits program 



variables only exist in there block (a block is the things surrounded by braces ie `{ int something }`)



General format of program should be

```
#include directives
#definedirectives
type definitions
external variables
function prototypes
definition of main
definitions of other functions
```

## Quizzes

Online 20 min quizzes with 15 question open book. 

**contains trick questions**

(11 quizzes total)

## Labs

Labs are once a week and genuinely fun most of the time

Time it takes to complete each lab various greatly week by week

(12 labs total)

## Assignments

There are two assignments that take plenty of time and are only worth bonus marks

## Final

1 two sided piece on paper as cheat sheet