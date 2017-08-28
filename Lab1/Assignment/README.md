# Math Library for MSP430
This library is processor ambiguous. This library is meant to be used as an abstraction layer in systems which recieve math operations from a communication such as UART.

## Dependencies
This library only depends on having the processor specific header file included in the main file. An example of this is MSP430.h for Texas Instruments MSP430 based processors.

## Usage
After including the math.h and math.c files in the same working directory as your project, you need to simple call the following function to perform the require operation:
```c
Math(int1, int2, operator);
```

### Valid Inputs

#### int1, int2
16-bit signed integers
#### operator
char which is valid for the following values ['+', '-', '*', '/', '%']. Math() will return Null if this input it invalid.

## Functions

### Add (char = '+')
int1 will be added to int2 and function will return the sum as a signed integer.
#### Example (10 + 20)
```c
Math( 10, 20, '+');
```

### Subtract (char = '-')
int 2 will be subtracted from int 1 and function will return the difference as a signed integer.
#### Example (10 - 20)
```c
Math( 10, 20, '-');
```

### Multiply (char = '*')
int 1 will be multiplied by int2 and function will return the difference as a signed integer.
#### Example (10 * 20)
```c
Math( 10, 20, '*');
```

### Divide (char = '/')
int1 will be integer divided by int2. This will only return the quotient as an integer.
#### Example (10 / 2)
```c
Math( 10, 2, '/');

## Known Errors
Currently there is no method of returning whether or not the returned value is signed. This means that operations such as "3-5" could be interpreted as +2 or -2.

## Tasks
- [x] Implment basic math operations
- [ ] Add support for the return of negative numbers
- [ ] Add input flag which can indicate whether to return an unsigned int or a char
