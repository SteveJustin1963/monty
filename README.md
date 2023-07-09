# MONTY

https://github.com/jhlagado/monty/tree/main

# User Guide for MONTY Programming Language

## Monty: An Intuitive and Readable Reverse Polish Notation (RPN) Language
This guide presents a comprehensive overview of the commands and operators available in the MONTY programming language. MONTY is designed to be user-friendly, employing a Reverse Polish Notation (RPN) approach. It incorporates familiar symbols and follows conventions from the C programming language when applicable. Monty is an ongoing project, conceptualized as a solution to overcome perceived limitations in Mint. A reverse polish notation (RPN) based language like Mint, Monty sets itself apart by prioritizing readability. Monty leverages intuitive symbols for operations, commonly following the conventions of the C programming language, which significantly enhances code comprehensibility.



## Functions and Variables

MONTY allows the definition of functions using the `:` operator, eliminating the need for explicit variable assignment. These functions are anonymous, meaning they do not require specific names. However, if you know the function's address, you can execute it using the `^` operator.

To define a function, use the `:` operator followed by lowercase letters (a..z) representing the function arguments. These arguments are distinct from global variables and can be accessed within the function body by prefixing them with `$`.

Example:
```
:mcx { $m $x * $c + } ; f=
```

In this example, the `mcx` function takes three arguments: `m`, `c`, and `x`. The function body multiplies `m` and `x`, then adds `c` to the result. The resulting function is stored in the variable `f`.

To call a function with specific argument values, use the `^` operator:

Example:
```
1 c 5 f^ y=
```

In this example, the values `1`, `c`, and `5` are passed as arguments to the `f` function. The result of the function is stored in the variable `y`.

### Global Variables

In addition to function arguments, MONTY supports the use of global variables within functions. These global variables can be accessed and modified from within the function body.

### Mathematical Example

Let's illustrate the usage of functions and global variables with a mathematical example of a straight line function `f(x) = mx + c`. Here, `m` represents the slope, `c` is the y-intercept, and `x` is the input.

To define the function `f`, use the `:` operator and specify the arguments `m`, `c`, and `x`. Within the function body, perform the necessary calculations to determine the value of `f(x)`.

```Monty
:mcx { $m $x * $c + } ; f=
```

To calculate the value of `f(x)` for specific `m`, `c`, and `x` values, pass them as arguments to the `f` function using the `^` operator. The result is stored in a variable, such as `y`.

```Monty
1 c 5 f^ y=
```


 
### Blocks and Conditional Structures in Monty
In Monty, blocks of code enclosed within { } are executed later with ^. For example:

```
> { 1 2 + . }^
3
```

Monty uses the ? symbol for conditional structures. For instance, to print "hello" if 3 is greater than 2, you can write:

```
> 3 2 > { "hello" .s } ?
```
Monty also supports "if..else" structures using ??:

```
> 3 2 >
```



### 1. Values

Values in this language can be represented in several forms:

- Integers: `1`, `2`, `123`, `0`, `-1`
- Hexadecimal: `#10`, `#FF`
- String characters: `'a'`, `'\\''`
- String characters: `"abc"`, `"hello"`
- Boolean values: `/f`, `/t`

Examples:

```
> 1 .
1

> 'a' /h.
#61

> /f .
0
```

### 2. Variable Assignment

Assigning a variable is done using `=` operator.

Example:

```
> 1a= a .
1
```

### 3. Arithmetic Operations

Arithmetic operations include addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`). The language also supports modulus (`%`) and negative `_`.

Examples:

```
> 1 2 + .
3

> 7 3 / _ .
1

> 10 1 >> .
5
```

### 4. Logical Operations

Logical operations include `&` (AND), `|` (OR), `==` (equality), `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to).

Examples:

```
> 3 5 & .
1

> 2 3 == .
0

> 2 2 <= .
-1
```

### 5. Bitwise Operations

Bitwise operations include `<<` (bitwise left shift), `>>` (bitwise right shift).

Examples:

```
> 3 1 << .
6

> 10 1 >> .
5
```

### 6. Conditional Statements

Conditional execution is represented using `{}` brackets and the `?` or `??` operators.

Examples:

```
> 5 /f {10} ? .
5

> 1 /t {10}{20} ?? + .
11
```

### 7. String Manipulation

** NEEDS WORK **
Strings are an important part of any programming language. In MONTY, strings are represented between double quotes `"` and characters between single quotes `'`. The language offers multiple operations to handle strings, including concatenation, indexing, conversion, comparison, and potentially more. 

The language support basic string manipulations. String content (`/c`), string hex representation (`/h`), and ASCII decimal representation (`/ad`).

Example:
```
> 'A' /ad .
65
```
This command is converting the ASCII character 'A' into its decimal ASCII value. ASCII (American Standard Code for Information Interchange) is a character encoding standard that represents text in computers and other devices that use text. Each character in the ASCII standard corresponds to a number from 0 to 127. For example, the ASCII value for 'A' is 65, which is what is being returned by the command.


Example:
```
> #4321 /h. /c/vB 0% .
#23
```

- `#4321 /h.`: This operation converts the hexadecimal value `4321` into a string. Hexadecimal is a number system with a base of 16, using digits from 0 to 9 and letters from A to F to represent the values 10 to 15. The output of this operation is the string representation of the hexadecimal value `4321`.

- `/c/vB`: These operations ....

- `0% .`: This operation is used to index the string, . The `0%` operation is taking the first character from the string resulting from the previous operations.


### Supported String Operations

MONTY supports a variety of string operations that are common in many programming languages, such as:

- Concatenation: Joining two or more strings into one.
- Indexing: Accessing individual characters in a string.
- Conversion: Changing strings into other data types and vice versa.
- Comparison: Comparing two strings to determine if they're equal.

### String Concatenation

You can concatenate, or combine, strings in MONTY using the `+` operator. This operation will join two or more strings into a single string.

Example:

```
> "hello" "world" + .
"helloworld"
```

### String Indexing

MONTY supports accessing individual characters of a string by their position in the string. The `%` operator is used to get the character at the specified index. Remember that string indexing starts from `0`.

Example:

```
> "hello" 0% .
'h'
```

### Conversion between Strings and Other Data Types

MONTY provides operations to convert strings to and from other data types. For example, the `/h` operation can convert a single character into its hexadecimal ASCII value, and the `/ad` operation converts it to the decimal ASCII value.

Example:

```
> 'A' /ad .
65
```

### String Comparison

String comparison in MONTY is done using the `==` operator. This will compare two strings and return `-1` if they are equal, and `0` if they are not. Note that this comparison is case-sensitive.

Example:

```
> "hello" "world" == .
0

> "hello" "HELLO" == .
0
```

### Other String Operations

....



### 8. Array Operations

Arrays can be represented using `[]` brackets, and elements can be accessed using the `%` operator. The length of the array can be got with the `/s` size operator

Examples:

> [10 20 30 40] /s .
> 4

```
> [10 20 30] 1% .
20

> 1 10 20 :iab{[{$a}{$b}] $i%^};^ .
20
```

### 9. Loops and Iteration

** NEEDS WORK **

MONTY includes a basic looping structure, which can be used with an iterator variable `i`. This allows for repetitive execution of commands, a feature essential for any programming language.

Example:

```
> 3i= ( i i-- i/br )^ + + .
6
```

In this example, `3i=` sets up a loop that iterates three times. The iterator variable `i` starts at 3 and decrements by 1 each time (`i--`). 

The `(` and `)^` symbols denote the start and end of the loop block. The `i/br` command breaks the loop if `i` becomes zero.

The `+ +` operation at the end adds the values returned from each iteration. 

In this case, the loop executes three times (for `i` values of 3, 2, and 1), and the result `6` is the sum of these values.

### Loops and Iteration (Advanced)

In addition to basic iterations, MONTY also supports more complex operations within the loop structures. In the example below, we demonstrate the utilization of nested loops for multiplication.

Example:

```shell
> 3i= ( 4j= ( i j * . j j-- j/br )^ i i-- i/br )^ .
3 4 *
12
3 3 *
9
3 2 *
6
3 1 *
3
2 4 *
8
2 3 *
6
2 2 *
4
2 1 *
2
1 4 *
4
1 3 *
3
1 2 *
2
1 1 *
1
```

In this example, `3i=` sets up an outer loop that iterates three times with `i` starting at 3 and decrementing by 1 each time (`i--`). Similarly, `4j=` sets up an inner loop that iterates four times with `j` starting at 4 and decrementing by 1 each time (`j--`).

The command `i j * .` multiplies the current values of `i` and `j` and prints the product. This command is executed at each iteration of the inner loop.

The `j j-- j/br` command decrements `j` and breaks the inner loop if `j` becomes zero, while the `i i-- i/br` command decrements `i` and breaks the outer loop if `i` becomes zero.

This setup generates a simple multiplication table for numbers 1 to 3. For instance, when `i` is 3 and `j` is 4, the multiplication `3 4 *` returns `12`. Similarly, when `i` is 2 and `j` is 3, the multiplication `2 3 *` returns `6`, and so on.




### 10. Increment and Decrement

The increment (`++`) and decrement (`--`) operations can be applied to variables. They increase or decrease the value of the variable by 1, respectively.

Examples:

```
 > 1a= a++ a .
2

 > 3a= a-- a .
2
```

### 11. Exclusive OR

The `/x` operator seems to perform an exclusive OR (XOR) operation on two values.

Examples:

```
 > 3 5 /x .
6

 > 3a= 5 a/x a= a .
6
```

### 12. Nested and Conditional Assignments

The `:var{}` construct seems to be a conditional assignment operator that only assigns a new value to a variable if the condition within the brackets is met.

Examples:

```
 > 5 :a{$a};^ .
5

 > :ab{$b $a}; x= 10 15 x^ - .
5
```

### 13. Array Operations

The construct `1%` is used to get the element at index 1 from an array.

Examples:

```
 > [10 20 30] 1% .
20

 > [{10}{20}{30}] 0%^  .
10
```

### 14. Iteration over Arrays

The language supports iterating over arrays with a loop variable `i`.

Examples:

```
 > 3i= ( i i-- i/br )^ + + .
6

 > 0 j= 4 i= ( i j + j= i i-- i/br )^ j  .
10
```

### 15. Character Arithmetic

The language allows for arithmetic operations on character variables, adjusting their ASCII value.

Examples:

```
 > 'A' 1 - /ad .
0

 > 'z' 1 + /ad .
0
```

### 16. String Conversion

String conversion to hexadecimal (`/h`) and vice versa is supported, as well as conversion of a string's hexadecimal form to a byte array (`/c/vB`).

Examples:

```
 > #4321 /h. /c/vB 0% .
#23

 > -1. /c/vB 0% /h.
#2D
```

### 17. Conditional Execution

The `?` operator seems to work as a conditional operator, executing the code block in braces `{}` following it if the preceding condition is -1. It's often used with the `/f` (0) and `/t` (-1) flags.

Examples:

```
 > 5 /f{10} ? .
5

 > 5 /t{10} ? + .
15

 > 1 /f{10}{20} ?? + .
21

 > 1 /t{10}{20} ?? + .
11
```

### 18. Lookup Table Generation

The colon operator `:` appears to be used in generating a lookup table for use in subsequent operations. When used with other operators and special characters, it seems to define complex expressions that refer to lookup tables or sequences.

Examples:

```
 > : -2% /h.
#0000

 > :a -1% /h.
#0001

 > :a: -1% /h.
#0001

 > :a:b -1% /h.
#0102

 > ::b -1% /h.
#0101
```

### 19. Bitwise Operations

The language also supports bitwise operations like left shift (`<<`), right shift (`>>`), AND (`&`), OR (`|`).

Examples:

```
 > 3 1 << .
6

 > 10 1 >> .
5

 > 3 5 & .
1

 > 3 5 | .
7
```

### 20. Single Quote Character Conversion

Single quotes `'` seem to be used to get the ASCII value of a character.

Examples:

```
 > 'a' /h.
#61

 > '\\'' /h.
#27
```

### 21. Using Special Characters

The language uses special characters like `#`, `%`, `^`, and `/` to perform specific operations. `#` seems to be a prefix for hexadecimal numbers, `%` is a modulo operation or used for indexing arrays, `^` might be a dereference or an operator to resolve an expression and `/` is used with characters to indicate special flags or operations.

Examples:

```
 > #10 /h.
#10

 > #FF /h.
#FF

 > :a{2}; x= 1 x^ .
2

 > 123. /c/vB 1% /h.
#32
```

### 22. Comparison Operations

Comparison operations are supported, like equal (`==`), less than (`<`), greater than (`>`), less than or equal to (`<=`), and greater than or equal to (`>=`).

Examples:

```
 > 2 3 == .
0

 > 3 3 == .
-1

 > 1 2 < .
-1

 > 2 1 < .
0
```

### 23. Looping and Recursion

It's quite interesting to observe the loop and recursion handling within this language. For example:

```
 > 0 j= 4 i= ( i j + j= i i-- i/br )^ j  .
10
```

In this script, a loop-like behavior is implemented using decrement (`--`), branching (`/br`) and the dereference operator (`^`). The `^` operator doesn't just resolve expressions, it seems to support execution of enclosed expressions as well, serving a purpose similar to a function call in other languages.

### 24. Abstraction Over Types

The language appears to have a level of abstraction over data types. As seen from the examples, it doesn't distinguish between integers, characters, and booleans in many operations. This is especially evident in arithmetic and bitwise operations where you can add a boolean to an integer or perform bitwise operations on characters.

For example:

```
 > 1 /t{10}{20} ?? + .
11
```

In this script, `/t` is treated as -1 which is then considered as `1` during the addition operation.

### 25. Position Independent Code

One interesting aspect of this language is that it supports position-independent code. An expression can be assigned to a variable and then executed at any position in the code. For example:

```
 > 2 :a= 1 a^ .
2
```

In this example, `2` is assigned to the variable `a` and then the code pointed by `a` is executed later with `a^`. This makes the language flexible and versatile for scripting complex behaviors.

### 26. Introspection

This language has a level of introspection. The `/ad` operator seems to return the internal address of a variable which can be very useful in certain contexts such as debugging or creating self-modifying code.

Example:

```
 > 'z' /ad .
VARS + (("z"-"a")+("Z"-"A")+1)*2
```

### 27. Unconventional Encoding

The language uses a unique way of encoding data into sequences of characters and numbers using operators like `.` and `/c/vB`.

Example:

```
 > `A`.s /c/vB 0% .
65
```

## Factorial of a number using recursion. 
Factorial of a number is the product of all positive integers less than or equal to that number. In mathematical terms, the factorial of a number n is denoted as n!, where

n! = n*(n-1)*(n-2)*...*3*2*1

For example, the factorial of 5 is 5! = 5 * 4 * 3 * 2 * 1 = 120.

Now, let's implement this in Monty:

```Monty
# This function calculates the factorial of a number recursively
:factorial { 
  $n 2 <  # Check if the input number is less than 2
  { 
    1  # If yes, return 1 as the factorial of 1 and 0 is 1
  } 
  { 
    $n $n 1 - factorial^ *  # If no, return n multiplied by the factorial of (n-1)
  } 
  ??  # Perform if-else
} ;
```

You can store the function in a variable, F, and call it:

```Monty
:factorial { $n 2 < { 1 } { $n $n 1 - factorial^ * } ?? } ; F=
```

Now, let's call this function with an input value of 5:

```Monty
5 F^ .
```

This should return 120.

Explanation:

1. The command `:factorial` defines a function named "factorial". 

2. Inside the function, we have an if-else structure (denoted by `??`) that checks if the input number n (accessed by `$n`) is less than 2. 

3. If it is, it returns 1. This is because the factorial of 1 and 0 is 1.

4. If it's not less than 2, it calculates the factorial recursively by multiplying the number n by the factorial of n-1. It calls the factorial function recursively using `factorial^`.

5. The function is stored in the variable F with `F=`.

6. Finally, the function is called with an input of 5 using `5 F^ .`. 

Remember, all the steps are executed in reverse Polish notation, where operators follow their operands.

## Fibonacci sequence using a loop and arrays.

The Fibonacci sequence is a series of numbers in which each number is the sum of the two preceding ones, usually starting with 0 and 1. So, the sequence goes: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, and so forth.

```Monty
# This function generates the Fibonacci sequence
:fibonacci {
  $n 2 < { [0 1] } { [0 1] $n 2 - i= ( $array $i 1% $array $i 2% + $array /a array= i i 1 + = )^ $array } ??
} ;
```

Store the function in a variable, F, and call it:

```Monty
:fibonacci { $n 2 < { [0 1] } { [0 1] $n 2 - i= ( $array $i 1% $array $i 2% + $array /a array= i i 1 + = )^ $array } ?? } ; F=
```

Let's call this function with an input value of 10 to generate the first 10 numbers in the Fibonacci sequence:

```Monty
10 F^ .
```

This should return [0, 1, 1, 2, 3, 5, 8, 13, 21, 34].

Explanation:

1. The command `:fibonacci` defines a function named "fibonacci".

2. Inside the function, we have an if-else structure (denoted by `??`) that checks if the input number n (accessed by `$n`) is less than 2.

3. If it is, it returns an array with the first two numbers of the Fibonacci sequence, [0, 1].

4. If it's not less than 2, it initializes an array with [0, 1] and initializes a counter i with the value of n-2. 

5. Then, it enters a loop (denoted by `()`), which is run by `^`, and executes the code block inside it n-2 times.

6. In each iteration of the loop, it calculates the next number in the Fibonacci sequence by adding the last two numbers in the array (accessed by `$array $i 1%` and `$array $i 2%`), appends it to the array with `$array /a`, and increments the counter i by 1.

7. Finally, it returns the array with the first n numbers in the Fibonacci sequence.

8. The function is stored in the variable F with `F=`.

9. Finally, the function is called with an input of 10 using `10 F^ .`.

Remember, all the steps are executed in reverse Polish notation, where operators follow their operands.

## Merge two sorted arrays into a sorted array. 
This is a common task in many algorithms such as mergesort.

Here's the function that performs the merge operation:

```Monty
:merge {
  $array1 $array2 $array1_size $array2_size
  $i $j $k 0 =
  ( 
    $i $array1_size < $j $array2_size < && 
    { 
      $array1 $i% $array2 $j% <=
      { $array1 $i% $result_array $k /a = i i 1 + = }
      { $array2 $j% $result_array $k /a = j j 1 + = }
      ??
      k k 1 + =
    }
    $i $array1_size < 
    { 
      $array1 $i% $result_array $k /a = i i 1 + = k k 1 + =
    } 
    ?
    $j $array2_size < 
    { 
      $array2 $j% $result_array $k /a = j j 1 + = k k 1 + =
    } 
    ?
    $i $array1_size >= $j $array2_size >= && /br 
  )^ 
  $result_array
} ; 
```

Here's how we can store it in a variable M and call it:

```Monty
:merge { $array1 $array2 $array1_size $array2_size $i $j $k 0 = ( $i $array1_size < $j $array2_size < && { $array1 $i% $array2 $j% <= { $array1 $i% $result_array $k /a = i i 1 + = } { $array2 $j% $result_array $k /a = j j 1 + = } ?? k k 1 + = } $i $array1_size < { $array1 $i% $result_array $k /a = i i 1 + = k k 1 + = } ? $j $array2_size < { $array2 $j% $result_array $k /a = j j 1 + = k k 1 + = } ? $i $array1_size >= $j $array2_size >= && /br )^ $result_array } ; M=
```

To call this function with two arrays [1, 3, 5] and [2, 4, 6], we do:

```Monty
[1 3 5] array1= 3 array1_size= [2 4 6] array2= 3 array2_size= M^ .
```

This should return [1, 2, 3, 4, 5, 6].

Explanation:

1. The command `:merge` defines a function named "merge".
2. Inside the function, we initialize i, j, and k to 0. These will be used as indexes for array1, array2, and result_array respectively.
3. We then start a loop `( )^`, which continues until both i and j are not less than their respective array sizes (`$i $array1_size >= $j $array2_size >= && /br`).
4. Inside the loop, we first check if the current elements of array1 and array2 are both less than their respective sizes. If they are, we compare the current elements of array1 and array2. If the current element of array1 is less than or equal to the current element of array2, we append it to result_array and increment i and k. Otherwise, we append the current element of array2 to result_array and increment j and k.
5. We then check if i is less than array1_size. If it is, we append the current element of array1 to result_array and increment i and k.
6. Similarly, we check if j is less than array2_size. If it is, we append the current element of array2 to result_array and increment j and k.
7. Once the loop ends, we return result_array, which is a sorted array that contains all the elements of array1 and array2.

## QuickSort algorithm 
QuickSort is an efficient sorting algorithm that uses a divide and conquer strategy. Given an array, it partitions the array around a pivot element, sorting values around the pivot, and then recursively applies the algorithm to the sub-arrays.

First, let's define a helper function `swap` to exchange elements in an array:

```Monty
:swap {
  $array $i $j
  $array $i% $temp =
  $array $j% $array $i /a =
  $temp $array $j /a =
} ; S=
```

Now, let's define the `partition` function, another helper function that will help to split the array around the pivot:

```Monty
:partition {
  $array $low $high
  $array $high% $pivot =
  $low $i =
  $low $high < {
    $array $high% <= {
      $array $i $array $high /swap^
      i i 1 + =
    }
    high high 1 + =
  } ?
  $array $i $array $high /swap^
  $i
} ; P=
```

Finally, the QuickSort function itself:

```Monty
:quickSort {
  $array $low $high
  $low $high <= {
    $array $low $high /partition^ $pi =
    $array $low $pi 1 - /quickSort^
    $array $pi 1 + $high /quickSort^
  } ?
} ; Q=
```

To call QuickSort on an array `[10, 7, 8, 9, 1, 5]`, we would do:

```Monty
[10, 7, 8, 9, 1, 5] array= 0 array_size= array 0 array_size 1 - Q^ .
```

This should return `[1, 5, 7, 8, 9, 10]`.

Explanation:

1. The `swap` function is a simple utility that swaps elements at indices i and j in an array.

2. The `partition` function takes in an array and two indices, low and high. It partitions the elements in the array around the pivot element (the element at the high index), so that all elements less than the pivot come before all elements greater than the pivot. It returns the index of the pivot in the partitioned array.

3. The `quickSort` function takes in an array and two indices, low and high. It uses the `partition` function to partition the array around a pivot, and then recursively calls itself on the two halves of the array (the elements before the pivot and the elements after the pivot).

 

 
