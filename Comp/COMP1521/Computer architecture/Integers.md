## Bases
The amount of symbols we have to represent numbers is completly arbetray. Instead of the standard 10 digit system were we use the symbols `0123456789` we could just use the first 2, `01`. 
The amount of symbols we chose to represent our numbers is called the **Base**.

Common bases are bellow:

| **Basis**   | symbols            | 54     |
| ----------- | ------------------ | ------ |
| Decimal     | `0123456789`       | 54     |
| Binary      | `01`               | 110110 |
| Octal       | `01234567`         | 66     |
| Hexadecimal | `0123456789ABCDEF` | 36     |
When we write a number, if it is not clear which base we are writing it in we write the base in the subscript. 

Eg: 54 in base 2 we get $110110_2$

When we do not have access to subscripts such as in code we can also distinguish between them by a prefix
`0x` - hex
`0b` - binary
`0`  - octal
Otherwise it is decimal

### Conversion
To convert between bases we use the fact that for a number with base $B$ the $n$th digit represents $B^{n-1}$. So for the binary number `101011` we get the 3rd digit is worth $0\times 2^2 = 0\times4 = 0$ whereas the 4th digit is worth
$1 \times 2^3 = 8$.

Thus when converting form one base to another we go through from the highest power of the new base and ask `how many times does this number go into the original number` that new number is the first digit of the converted number. We then subtract it then repeat. An example is bellow

#### $54_{10} \rightarrow$ base 2
Running converted number: `000000`
left over: `54`
- How many 32s in 54? $\rightarrow$ 1
Running converted number: `100000`
left over: `54 - 32 = 22`
- How many 16s in 22? $\rightarrow$ 1
Running converted number: `110000`
left over: `22 - 16 = 6`
- How many 8s in 6? $\rightarrow$ 0
Running converted number: `110000`
left over: `6 = 6`
- How many 4s in 6? $\rightarrow$ 1
Running converted number: `110100`
left over: `6 - 4 = 2`
- How many 2s in 2? $\rightarrow$ 1
Running converted number: `110110`
left over: `2 - 2 = 0`
- How many 1s in 0? $\rightarrow$ 0
Running converted number: `110110`
#### Conversion shortcuts
When converting to bases that are powers of your current base we can employ a shortcut to make our like easier.

We group the digits into groups of size $n$ where if $O$ is our old base and $B$ is the new base then $B = O^n$.

We then can convert each group into a single digit. 
##### $10110111_2 \rightarrow$ base 16
1. group the numbers
`1011` and `0111`
2. convert each group
`1011` $\rightarrow$ $8 + 2 + 1 = 11_{10} = A_{16}$
`0111` $\rightarrow$ $4 + 2 + 1 = 7_{16}$
3. recombine
$A7_{16}$

## Integer representation
We represent integers in memory in base 2.
### Unsigned
for Unsigned integers we simply represent numbers in

### Signed

For negative numbers, to simplify the cpu architecture we use two's complement.

Two's complement represents $-b$ as $2^N - b$ where $N$ is the number of bits being used to represent the numbers. This is really useful as it makes addition between two number the same operation no matter if it is negative or positive.

Eg:
in $8$ bits $-54$ is represented as:
`2^8 - 54`
$$
\begin{equation*}\begin{array}{c}
\phantom{-}100000000\\
\underline{-\phantom{999}110110}\\
\phantom{-}011001010\\
\end{array}\end{equation*}
$$
