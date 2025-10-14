## C types
Floating point numbers are designed to store decimal numbers.

We can use the types:
- `float` - 32 bits
- `double` - 64 bits
- `long double` - 128 bits

C stores decimals as doubles
## In memory
The big idea of floating point numbers is to represent our numbers in scientific notation on the hardware level.

We take our memory and divide it into 3 regions according to the IEEE standards:

| region          | float length | Double length |
| --------------- | ------------ | ------------- |
| sign bit        | 1            | 1             |
| exponent bits   | 8            | 11            |
| fractional bits | 23           | 52            |
Note: We do not need to store the first digit of the fractional part because we know it will always be 1 if we normalize it into the exponent.

To represent negative exponents we store our actual value + a bias like so `exponent = x + b` where the bias is usually 127 for floats. This means that to store an exponent of 5 we put `127 + 5 = 132` into the exponent.

### Special cases

| Value              | Exponent | Fraction  |
| ------------------ | -------- | --------- |
| 0                  | all 0    | all 0     |
| $\infty / -\infty$ | all 1    | all 0     |
| nan                | all 1    | not all 0 |
## Accuracy
Because we represent our number in scientific notation the distance between numbers we can represent get larger as the exponent gets larger.

This means eventually as we get to the largest numbers we can represent we end up not being able to distinguish numbers less than 1 apart.

This can lead to weird bugs.
## Printing
We can print with the following tags:

| Tag   | style                                         |
| ----- | --------------------------------------------- |
| %lf   | Prints as a decimal                           |
| %le   | Prints in scientific notation with a little e |
| %lg   | Do whatever the computer thinks is best       |
| %.8lf | Print 8 decimal places                        |
