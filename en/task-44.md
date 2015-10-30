After solving [Dice Rolling](./dice-rolling), we already know how to convert fractional value
between `0.0` and `1.0` to an integer number from within the specific range - for example
to values between `1` and `6`, simulating the throwing of the die.

However, many programming languages (like **C/C++**, **PHP**, **Pascal**) use random number generator
which on contrary gives only integer values in the range
from `0` to some (very large) maximum. How to convert such numbers to dice points?

It happens that this case is even simpler. We can use the following approach:

1. Divide the random value `R` by the `N` (number of distinct values we want - e.g. `6` for dice) and take
    the remainder. This remainder is necessarily the integer value in the range from `0` to `N - 1`.
2. Now to shift it to the necessary range, simply add `1` (i.e. the minimum of the range we want) - and you'll get the
    value in the range from `1` to `N`.

This method is not well precise if `N` is not small enough in compare to `max` of the generator. However it will be all
right for most everyday needs (tossing coins, rolling dice, shuffling cards etc.)

To have practice, let us proceed with the following exercise:

**Input data** will contain the number of test-cases (dice throws) in the first line.  
Next lines will have test-cases - each consisting of two random integer numbers - for throwing a pair of dice. These
numbers are non-negative (from `0` to some value above `2,000,000,000`) and they should be converted to dice points
using the algorithm proposed above.  
**Answer** should contain the sum of each throw of the pair of dice, values should be separated with spaces.

Example:

	input data:
	7
	193170145 1912748246
	753156389 614113621
	1824520917 53700559
	1288077384 911939603
	1939066598 1695763253
	1905581606 1811712139
	878644967 1090885451
	
	
	answer:
	5 8 6 7 9 5 12
	