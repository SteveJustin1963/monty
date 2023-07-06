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


