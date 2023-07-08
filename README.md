# monty
https://github.com/jhlagado/monty/tree/main




1. Initialize memory variables and constants.
2. Define functions for character input/output and string manipulation.
3. Implement the nesting calculation function.
4. Create a jump table for command execution.
5. Define functions for control flow and interpreter.
6. Handle various special commands like backspace, edit, re-edit, and print stack.
7. Implement the main interpreter loop.
8. Define functions to handle opcode execution.
9. Implement other functions and blocks for specific operations.
10. Start the interpreter by initializing memory and printing the program count.
11. Enter the main interpretation loop.
12. Continuously read input, interpret commands, and execute them.
13. Process whitespace and macro/control characters.
14. Execute the input TIB as code.
15. Handle special cases like if-else conditions, executing blocks and lambdas, performing hash operations, and converting numbers.
16. Print the stack and handle error conditions.
17. Handle character input, including backspace, carriage return, and special control characters.
18. Repeat the interpretation loop until the end of input is reached.
19. Exit the interpreter.


```
# Variables
var vTemp1, vTemp2, vNumBase, vBufPtr, vHeapPtr, vTIBPtr, vNext

# Constants
const DQUOTE = "\""
const NUL = 0
const CTRL_E = 5
const CTRL_H = 8
const CTRL_J = 10
const CTRL_S = 19
const TIB_SIZE = 256
const STACK_SIZE = 1024

# Memory Initialization
initialize_memory():
    vNext = 0x0000
    vTemp1 = 0
    vTemp2 = 0
    vNumBase = 10
    vBufPtr = buffer_start_address
    vHeapPtr = heap_start_address
    vTIBPtr = TIB_start_address

# Character Input/Output
getchar():
    # Read a character from input
    # Returns the ASCII value of the character

putchar(char):
    # Output a character to the console
    # char: ASCII value of the character

prtstr(str):
    # Print a null-terminated string
    # str: Pointer to the start of the string

flushBuffer():
    # Flushes the buffer to output

printStr(str):
    # Print a null-terminated string
    # str: Pointer to the start of the string

crlf():
    # Prints a newline to output

# Nesting Calculation
nesting(char, nest):
    # Calculate the nesting level
    # char: Character to be tested
    # nest: Nesting value (initially 0)
    # Returns the updated nesting value

# Command Execution
jumpTable(char):
    # Jump table for command execution
    # char: Character representing the command
    # Returns the address of the command routine

# Control Flow and Interpreter
prompt():
    # Prints the interpreter prompt

error():
    # Error handling routine

init():
    # Initialize system variables and variables array

start():
    # Start the interpreter
    # Initialize memory and print the program count

interpret():
    # Main interpreter loop

next():
    # Increment the instruction pointer and fetch the next character

run():
    # Execute the current command

backSpace_():
    # Handle backspace key press

edit_():
    # Edit the last line

reEdit_():
    # Re-edit the last line

printStack_():
    # Print the stack

interpret2():
    # Continue the interpretation after getting input

interpret3():
    # Process each character in the input TIB

interpret4():
    # Store the input TIB in memory and set up for interpretation

interpret5():
    # Handle whitespace and macro/control characters

interpret6():
    # Handle character input from the console

interpret7():
    # Handle carriage return character

interpret8():
    # Interpret the input TIB as code

# Opcode Handlers
opcode_handler1():
    # Handler for opcode 1

opcode_handler2():
    # Handler for opcode 2

# Other Functions and Blocks
bufferArray():
    # Handle buffer array operation

bufferNumber():
    # Handle buffer number operation (decimal or hex)

bufferDec():
    # Handle buffer decimal number operation

bufferDec0():
    # Handle decimal number conversion

bufferDec2():
    # Handle decimal number conversion

bufferHex():
    # Handle buffer hex number operation

bufferHex1():
    # Handle hex number conversion

bufferString():
    # Handle buffer string operation

bufferChar():
    # Handle buffer character operation

bufferXChars():
    # Handle buffer multiple characters operation

question():
    # Handle if-else condition

ifte():
    # Handle if-else condition

go():
    # Execute a block of code

go1():
    # Execute a block of code

go2():
    # Execute a block of code

goBlock():
    # Execute a block of code

goBlock1():
    # Execute a block of code

goBlock2():
    # Execute a block of code

goLambda():
    # Execute a lambda

goLambda1():
    # Execute a lambda

goLambda2():
    # Execute a lambda

goLambda3():
    # Execute a lambda

goLambda4():
    # Execute a lambda

goLambda5():
    # Execute a lambda

goLambda6():
    # Execute a lambda

goLambda7():
    # Execute a lambda

goLambda8():
    # Execute a lambda

hash():
    # Handle hash operation

hexnum():
    # Handle hex number conversion

upcase():
    # Convert a character to uppercase

lowcase():
    # Convert a character to lowercase

semicolon():
    # Handle semicolon operation

rparen():
    # Handle right parenthesis operation

args1A2L():
    # Handle args1A2L operation

args1A0L():
    # Handle args1A0L operation

partial():
    # Handle partial operation

printBuffer():
    # Print the buffer

printChars():
    # Print characters from buffer

printStack():
    # Print the stack

bufferDec1():
    # Handle decimal number conversion

bufferDec3():
    # Handle decimal number conversion

size():
    # Calculate the size of an object

bufferXChars0():
    # Handle buffer multiple characters operation

bufferXChars1():
    # Handle buffer multiple characters operation

nesting1a():
    # Toggle bit 7 of the nesting value

nesting1():
    # Handle nesting increment

nesting2():
    # Handle nesting increment

nesting3():
    # Handle nesting decrement

nesting4():
    # Handle nesting decrement

interpret5a():
    # Loop for character input

interpret6():
    # Handle character input from the console

initialize_memory()
start()
interpret()
```

## manual

# User Guide for Programming Language

## Introduction

This guide covers an unnamed language that includes a range of commands and operators. These commands provide functionality for variable manipulation, logical operations, mathematical computations, bitwise operations, conditional execution, string manipulation, and more.

## Commands and Operators

### 1. Values

Values in this language can be represented in several forms:

- Integers: `1`, `2`, `123`, `0`, `-1`
- Hexadecimal: `#10`, `#FF`
- String characters: `'a'`, `'\\''`
- Boolean values: `/f`, `/t`

Examples:
```c
    test "1", 1
    test "'a'", $61
    test "/f", false
```

### 2. Variable Assignment

Assigning a variable is done using `=` operator. 

Example:
```c
    test "1a= a", 1
```

### 3. Arithmetic Operations

Arithmetic operations include addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`). The language also supports modulus (`%`) and negative `_`.

Examples:
```c
    test "1 2 +", 3
    test "7 3 / _", 1
    test "10 1 >>", 5
```

### 4. Logical Operations

Logical operations include `&` (AND), `|` (OR), `==` (equality), `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to).

Examples:
```c
    test "3 5 &", 1
    test "2 3 ==", FALSE
    test "2 2 <=", TRUE
```

### 5. Bitwise Operations

Bitwise operations include `<<` (bitwise left shift), `>>` (bitwise right shift).

Examples:
```c
    test "3 1 <<", 6
    test "10 1 >>", 5
```

### 6. Conditional Statements

Conditional execution is represented using `{}` brackets and the `?` or `??` operators.

Examples:
```c
    test "5 /f{10} ?", 5
    test "1 /t{10}{20} ?? +", 11
```

### 7. String Manipulation

The language seems to support basic string manipulations, including string length (`/s`), string content (`/c`), string hex representation (`/h`), and ASCII decimal representation (`/ad`).

Examples:
```c
    test "[10 20 30 40] /s", 4
    test "'A' /ad", 65
    test "#4321 /h. /c/vB 0%", $23
```

### 8. List Operations

Lists can be represented using `[]` brackets, and elements can be accessed using the `%` operator.

Examples:
```c
    test "[10 20 30] 1%", 20
    test "1 10 20 :iab{[{$a}{$b}] $i%^};^", 20
```

### 9. Loops and Iteration

The language seems to include a basic looping structure, with an iterator variable `i`.

Example:
```c
    test "3i= ( i i-- i/br )^ + +", 6
```


### 10. Increment and Decrement

The increment (`++`) and decrement (`--`) operations can be applied to variables. They increase or decrease the value of the variable by 1, respectively.

Examples:
```c
    test "1a= a++ a", 2
    test "3a= a-- a", 2
```

### 11. Exclusive OR

The `/x` operator seems to perform an exclusive OR (XOR) operation on two values.

Examples:
```c
    test "3 5 /x", 6
    test "3a= 5 a/x a= a", 6
```

### 12. Nested and Conditional Assignments

The `:var{}` construct seems to be a conditional assignment operator that only assigns a new value to a variable if the condition within the brackets is met.

Examples:
```c
    test "5 :a{$a};^", 5
    test ":ab{$b $a}; x= 10 15 x^ -", 5
```

### 13. Array Operations

The construct `1%` is used to get the element at index 1 from an array.

Examples:
```c
    test "[10 20 30] 1%", 20
    test "[{10}{20}{30}] 0%^ ", 10
```

### 14. Iteration over Arrays

The language supports iterating over arrays with a loop variable `i`.

Examples:
```c
    test "3i= ( i i-- i/br )^ + +", 6
    test "0 j= 4 i= ( i j + j= i i-- i/br )^ j ", 10
```

### 15. Character Arithmetic

The language allows for arithmetic operations on character variables, adjusting their ASCII value.

Examples:
```c
    test "'A' 1 - /ad", NUL
    test "'z' 1 + /ad", NUL
```

### 16. String Conversion

String conversion to hexadecimal (`/h`) and vice versa is supported, as well as conversion of a string's hexadecimal form to a byte array (`/c/vB`).

Examples:
```c
    test "#4321 /h. /c/vB 0%", $23
    test "-1. /c/vB 0%", $2D
```

 

### 17. Conditional Execution

The `?` operator seems to work as a conditional operator, executing the code block in braces `{}` following it if the preceding condition is true. It's often used with the `/f` (false) and `/t` (true) flags.

Examples:
```c
    test "5 /f{10} ?", 5
    test "5 /t{10} ? +", 15
    test "1 /f{10}{20} ?? +", 21
    test "1 /t{10}{20} ?? +", 11
```

### 18. Lookup Table Generation

The colon operator `:` appears to be used in generating a lookup table for use in subsequent operations. When used with other operators and special characters, it seems to define complex expressions that refer to lookup tables or sequences.

Examples:
```c
    test ": -2%", $0000
    test ":a -1%", $0001
    test ":a: -1%", $0001
    test ":a:b -1%", $0102
    test "::b -1%", $0101
```

### 19. Bitwise Operations

The language also supports bitwise operations like left shift (`<<`), right shift (`>>`), AND (`&`), OR (`|`).

Examples:
```c
    test "3 1 <<", 6
    test "10 1 >>", 5
    test "3 5 &", 1
    test "3 5 |", 7
```

### 20. Single Quote Character Conversion

Single quotes `'` seem to be used to get the ASCII value of a character.

Examples:
```c
    test "'a'", $61
    test "'\\''", $27
```

### 21. Using Special Characters

The language uses special characters like `#`, `%`, `^`, and `/` to perform specific operations. `#` seems to be a prefix for hexadecimal numbers, `%` is a modulo operation or used for indexing arrays, `^` might be a dereference or an operator to resolve an expression and `/` is used with characters to indicate special flags or operations.

Examples:
```c
    test "#10", $10
    test "#FF", $FF
    test ":a{2}; x= 1 x^", 2
    test "123. /c/vB 1%", $32
```

### 22. Comparison Operations

Comparison operations are supported, like equal (`==`), less than (`<`), greater than (`>`), less than or equal to (`<=`), and greater than or equal to (`>=`).

Examples:
```c
    test "2 3 ==", FALSE
    test "3 3 ==", TRUE
    test "1 2 <", TRUE
    test "2 1 <", FALSE
```

 

### 23. Looping and Recursion

It's quite interesting to observe the loop and recursion handling within this language. For example:

```c
    test "0 j= 4 i= ( i j + j= i i-- i/br )^ j ", 10
```

In this script, a loop-like behavior is implemented using decrement (`--`), branching (`/br`) and the dereference operator (`^`). The `^` operator doesn't just resolve expressions, it seems to support execution of enclosed expressions as well, serving a purpose similar to a function call in other languages.

### 24. Abstraction Over Types

The language appears to have a level of abstraction over data types. As seen from the examples, it doesn't distinguish between integers, characters, and booleans in many operations. This is especially evident in arithmetic and bitwise operations where you can add a boolean to an integer or perform bitwise operations on characters. 

For example:

```c
    test "1 /t{10}{20} ?? +", 11
```

In this script, `/t` is treated as true which is then considered as `1` during the addition operation.

### 25. Position Independent Code

One interesting aspect of this language is that it supports position-independent code. An expression can be assigned to a variable and then executed at any position in the code. For example:

```c
    test "2 :a= 1 a^", 2
```

In this example, `2` is assigned to the variable `a` and then the code pointed by `a` is executed later with `a^`. This makes the language flexible and versatile for scripting complex behaviors.

### 26. Introspection

This language has a level of introspection. The `/ad` operator seems to return the internal address of a variable which can be very useful in certain contexts such as debugging or creating self-modifying code.

Example:

```c
    test "'z' /ad", VARS + (("z"-"a")+("Z"-"A")+1)*2
```

### 27. Unconventional Encoding

The language uses a unique way of encoding data into sequences of characters and numbers using operators like `.` and `/c/vB`.

Example:

```c
    test "`A`.s /c/vB 0%", 65
```
