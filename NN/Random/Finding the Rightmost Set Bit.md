
must know !
**Two's complement** is the most common [method of representing signed](https://en.wikipedia.org/wiki/Signed_number_representations "Signed number representations") (positive, negative, and zero) [integers](https://en.wikipedia.org/wiki/Integer_(computer_science) "Integer (computer science)") on computers,[[1]](https://en.wikipedia.org/wiki/Two's_complement#cite_note-1) and more generally, [fixed point binary](https://en.wikipedia.org/wiki/Fixed-point_arithmetic "Fixed-point arithmetic") values. Two's complement uses the [binary digit with the _greatest_ value](https://en.wikipedia.org/wiki/Most_Significant_Bit "Most Significant Bit") as the _sign_ to indicate whether the binary number is positive or negative; when the [most significant bit](https://en.wikipedia.org/wiki/Most_significant_bit "Most significant bit") is _1_ the number is signed as negative and when the most significant bit is _0_ the number is signed as positive. As a result, non-negative numbers are represented as themselves: 6 is 0110, zero is 0000, and -6 is 1010 (~6 + 1). Note that while the number of binary bits is fixed throughout a computation it is otherwise arbitrary.


import java.io.*;

class GFG {

    public static int getFirstSetBitPos(int n)
    {
        return (int)((Math.log10(n & -n)) / Math.log10(2)) + 1;
    }

    // Drive code
    public static void main(String[] args)
    {
        int n = 18;
        System.out.println(getFirstSetBitPos(n));
    }
}
// This code is contributed by Arnav Kr. Mandal



1. **Finding the Rightmost Set Bit**
The goal of the `getFirstSetBitPos` method is to find the position of the rightmost set bit (i.e., the bit with the value `1`) in the binary representation of a given integer `n`.

2. **`n & -n` Operation**
The expression `n & -n` isolates the rightmost set bit in `n`. Here's how it works:

- `-n` is the two's complement negation of `n`. In two's complement, `-n` is calculated as `~n + 1` where `~n` is the bitwise NOT of `n`.
- The result of `n & -n` gives a number where only the rightmost set bit in `n` is set, and all other bits are zero.
- 
For example:

- For `n = 18` (binary `10010`), `-n` would be `-18` (binary `01110` in 2's complement form).
- `n & -n` gives `00010` (binary), which isolates the rightmost set bit.

#### 3. **Calculating the Position**

The code uses logarithms to determine the position of the isolated bit:

- `Math.log10(n & -n)` calculates the base-10 logarithm of the isolated bit.
- `Math.log10(2)` is the base-10 logarithm of 2.
- Dividing these values gives the base-2 logarithm (position of the bit in binary) since `log_b(a) = log_k(a) / log_k(b)`, where `b` is the base we want (2 in this case) and `k` is the base we have (10 here).

Finally:

- Adding `1` adjusts for 1-based indexing (i.e., the position is typically counted starting from 1).

#### Example Calculation

For `n = 18`:

- `n = 18` in binary: `10010`
- `-18` in binary (in two's complement): `01110`
- `n & -n` isolates the rightmost set bit: `00010` (binary `2` in decimal)
- `Math.log10(2)` is approximately `0.3010`
- `Math.log10(2)` is approximately `0.3010`
- Therefore, `Math.log10(2) / Math.log10(2)` is `1`.
- Adding `1` gives the result `2`.

So, the position of the rightmost set bit in `18` is `2`, which is printed by the program.

### Summary

- **`n & -n`** isolates the rightmost set bit.
- **`Math.log10(n & -n) / Math.log10(2)`** calculates the position of that bit.
- **`+1`** adjusts for 1-based indexing.

The code provides an elegant way to determine the position of the rightmost set bit in a number using logarithms.



