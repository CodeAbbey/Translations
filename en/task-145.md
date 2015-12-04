Now all you need to do is a calculation of raising `A` to power of `B` with result taken by modulo `M`.

This operation is the cornerstone of many algorithms like generation of probable primes, generating keys for modern
cryptography etc.

_Though some languages have built-in functions for such calculation, of course it would be better **for you**
to find another approach!_

**Input data** will contain the number of testcases in the first line.  
Next lines will have three values for `A B M` each.  
**Answer** should give `(A^B)%M` for each case.

Example:

	input data:
	3
	14 28 219431273
	30 56 351887801
	43 47 289907803
	
	answer:
	5022695 292780914 140818938
