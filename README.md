# MONTY
https://github.com/jhlagado/monty/tree/main



## manual

# User Guide for MONTY Programming Language

## Introduction

This guide covers the range of commands and operators. These commands provide functionality for variable manipulation, logical operations, mathematical computations, bitwise operations, conditional execution, string manipulation, and more.
Between the quotes `"` is the input and after the comma `,` is the result placed on the stack whichc an be shown with `.`.


## Commands and Operators

### 1. Values

Values in this language can be represented in several forms:

- Integers: `1`, `2`, `123`, `0`, `-1`
- Hexadecimal: `#10`, `#FF`
- String characters: `'a'`, `'\\''`
- Boolean values: `/f`, `/t`

Examples:
  ``` 
      "1", 1
      "'a'", $61
      "/f", false
  ```

### 2. Variable Assignment

Assigning a variable is done using `=` operator. 

Example:
  ``` 
      "1a= a", 1
  ```

### 3. Arithmetic Operations

Arithmetic operations include addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`). The language also supports modulus (`%`) and negative `_`.

Examples:
  ``` 
      "1 2 +", 3
      "7 3 / _", 1
      "10 1 >>", 5
  ```

### 4. Logical Operations

Logical operations include `&` (AND), `|` (OR), `==` (equality), `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to).

Examples:
  ``` 
      "3 5 &", 1
      "2 3 ==", FALSE
      "2 2 <=", TRUE
  ```

### 5. Bitwise Operations

Bitwise operations include `<<` (bitwise left shift), `>>` (bitwise right shift).

Examples:
  ``` 
      "3 1 <<", 6
      "10 1 >>", 5
  ```

### 6. Conditional Statements

Conditional execution is represented using `{}` brackets and the `?` or `??` operators.

Examples:
  ``` 
      "5 /f{10} ?", 5
      "1 /t{10}{20} ?? +", 11
  ```

### 7. String Manipulation

The language seems to support basic string manipulations, including string length (`/s`), string content (`/c`), string hex representation (`/h`), and ASCII decimal representation (`/ad`).

Examples:
  ``` 
      "[10 20 30 40] /s", 4
      "'A' /ad", 65
      "#4321 /h. /c/vB 0%", $23
  ```

### 8. List Operations

Lists can be represented using `[]` brackets, and elements can be accessed using the `%` operator.

Examples:
  ``` 
      "[10 20 30] 1%", 20
      "1 10 20 :iab{[{$a}{$b}] $i%^};^", 20
  ```

### 9. Loops and Iteration

The language seems to include a basic looping structure, with an iterator variable `i`.

Example:
  ``` 
      "3i= ( i i-- i/br )^ + +", 6
  ```


### 10. Increment and Decrement

The increment (`++`) and decrement (`--`) operations can be applied to variables. They increase or decrease the value of the variable by 1, respectively.

Examples:
 ``` 
      "1a= a++ a", 2
      "3a= a-- a", 2
  ```

### 11. Exclusive OR

The `/x` operator seems to perform an exclusive OR (XOR) operation on two values.

Examples:
 ``` 
      "3 5 /x", 6
      "3a= 5 a/x a= a", 6
  ```

### 12. Nested and Conditional Assignments

The `:var{}` construct seems to be a conditional assignment operator that only assigns a new value to a variable if the condition within the brackets is met.

Examples:
 ``` 
      "5 :a{$a};^", 5
      ":ab{$b $a}; x= 10 15 x^ -", 5
  ```

### 13. Array Operations

The construct `1%` is used to get the element at index 1 from an array.

Examples:
 ``` 
      "[10 20 30] 1%", 20
      "[{10}{20}{30}] 0%^ ", 10
  ```

### 14. Iteration over Arrays

The language supports iterating over arrays with a loop variable `i`.

Examples:
 ``` 
      "3i= ( i i-- i/br )^ + +", 6
      "0 j= 4 i= ( i j + j= i i-- i/br )^ j ", 10
  ```

### 15. Character Arithmetic

The language allows for arithmetic operations on character variables, adjusting their ASCII value.

Examples:
 ``` 
      "'A' 1 - /ad", NUL
      "'z' 1 + /ad", NUL
  ```

### 16. String Conversion

String conversion to hexadecimal (`/h`) and vice versa is supported, as well as conversion of a string's hexadecimal form to a byte array (`/c/vB`).

Examples:
 ``` 
      "#4321 /h. /c/vB 0%", $23
      "-1. /c/vB 0%", $2D
  ```

 

### 17. Conditional Execution

The `?` operator seems to work as a conditional operator, executing the code block in braces `{}` following it if the preceding condition is true. It's often used with the `/f` (false) and `/t` (true) flags.

Examples:
 ``` 
      "5 /f{10} ?", 5
      "5 /t{10} ? +", 15
      "1 /f{10}{20} ?? +", 21
      "1 /t{10}{20} ?? +", 11
  ```

### 18. Lookup Table Generation

The colon operator `:` appears to be used in generating a lookup table for use in subsequent operations. When used with other operators and special characters, it seems to define complex expressions that refer to lookup tables or sequences.

Examples:
 ``` 
      ": -2%", $0000
      ":a -1%", $0001
      ":a: -1%", $0001
      ":a:b -1%", $0102
      "::b -1%", $0101
  ```

### 19. Bitwise Operations

The language also supports bitwise operations like left shift (`<<`), right shift (`>>`), AND (`&`), OR (`|`).

Examples:
 ``` 
      "3 1 <<", 6
      "10 1 >>", 5
      "3 5 &", 1
      "3 5 |", 7
  ```

### 20. Single Quote Character Conversion

Single quotes `'` seem to be used to get the ASCII value of a character.

Examples:
 ``` 
      "'a'", $61
      "'\\''", $27
  ```

### 21. Using Special Characters

The language uses special characters like `#`, `%`, `^`, and `/` to perform specific operations. `#` seems to be a prefix for hexadecimal numbers, `%` is a modulo operation or used for indexing arrays, `^` might be a dereference or an operator to resolve an expression and `/` is used with characters to indicate special flags or operations.

Examples:
 ``` 
      "#10", $10
      "#FF", $FF
      ":a{2}; x= 1 x^", 2
      "123. /c/vB 1%", $32
  ```

### 22. Comparison Operations

Comparison operations are supported, like equal (`==`), less than (`<`), greater than (`>`), less than or equal to (`<=`), and greater than or equal to (`>=`).

Examples:
 ``` 
      "2 3 ==", FALSE
      "3 3 ==", TRUE
      "1 2 <", TRUE
      "2 1 <", FALSE
  ```

 

### 23. Looping and Recursion

It's quite interesting to observe the loop and recursion handling within this language. For example:

 ``` 
      "0 j= 4 i= ( i j + j= i i-- i/br )^ j ", 10
  ```

In this script, a loop-like behavior is implemented using decrement (`--`), branching (`/br`) and the dereference operator (`^`). The `^` operator doesn't just resolve expressions, it seems to support execution of enclosed expressions as well, serving a purpose similar to a function call in other languages.

### 24. Abstraction Over Types

The language appears to have a level of abstraction over data types. As seen from the examples, it doesn't distinguish between integers, characters, and booleans in many operations. This is especially evident in arithmetic and bitwise operations where you can add a boolean to an integer or perform bitwise operations on characters. 

For example:

 ``` 
      "1 /t{10}{20} ?? +", 11
  ```

In this script, `/t` is treated as true which is then considered as `1` during the addition operation.

### 25. Position Independent Code

One interesting aspect of this language is that it supports position-independent code. An expression can be assigned to a variable and then executed at any position in the code. For example:

 ``` 
      "2 :a= 1 a^", 2
  ```

In this example, `2` is assigned to the variable `a` and then the code pointed by `a` is executed later with `a^`. This makes the language flexible and versatile for scripting complex behaviors.

### 26. Introspection

This language has a level of introspection. The `/ad` operator seems to return the internal address of a variable which can be very useful in certain contexts such as debugging or creating self-modifying code.

Example:

 ``` 
      "'z' /ad", VARS + (("z"-"a")+("Z"-"A")+1)*2
  ```

### 27. Unconventional Encoding

The language uses a unique way of encoding data into sequences of characters and numbers using operators like `.` and `/c/vB`.

Example:

 ``` 
      "`A`.s /c/vB 0%", 65
  ```
