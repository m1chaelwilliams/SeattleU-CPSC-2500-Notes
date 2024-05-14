

# Memory Layout

| 1 bits   | 8 bits       | 23 bits  |
| -------- | ------------ | -------- |
| Sign bit | Non-Fraction | Fraction |

# Sign Bit
Changes the sign of the number from positive to negative.

# Non-Fraction (The Exponent)
There is a bias to add. It is 127. So if you have an exponent of 8, you need to add $8 + 127$.

# Fraction
This represents the fraction part of the number. Take everything from the right of the first occurrence of 1. Fill in 0s for the remaining numbers.

# Converting from binary to decimal
1. Look at the first bit, it decides if the number if positive of negative.
2. Calculate the exponent's value.
	1. Subtract 127 to undo the bias.
3. Keep the last part the same.
	1. *You should get something along the lines of $2^n * 1.010101...$*
4. Move the decimal point over $n$ times.
5. Finally, calculate each side and convert them to decimals.
	1. On the left, calculate like normal.
	2. On the right, from left to right, go from $-1 \rightarrow n$


