## C types
Floating point numbers are designed to store decimal numbers.

We can use the types:
- `float` - 32 bits
- `double` - 64 bits
- `long double` - 128 bits

C stores decimals as doubles
## In memory
The big idea of floating point numbers is to represent our numbers in scientific notation on the hardware level.

We take our memory and divide it into 3 regions:

| region          | float length |     |
| --------------- | ------------ | --- |
| sign bit        | 1            |     |
| exponent bits   | 8            |     |
| fractional bits | 23           |     |
Note: We do not need to store the first digit of the fractional part because we know it will always be 1 if we normalize it into the exponent.

To represent negative exponents we store our actual value + a bias like so `exponent = x + b` where the bias is usually 127. This means that to store an exponent of 5 we put `127 + 5 = 132` into the exponent.


## Printing
We can print with the following tags:

| Tag   | style                                         |
| ----- | --------------------------------------------- |
| %lf   | Prints as a decimal                           |
| %le   | Prints in scientific notation with a little e |
| %lg   | Do whatever the computer thinks is best       |
| %.8lf | Print 8 decimal places                        |
