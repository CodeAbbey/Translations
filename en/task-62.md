<!-- #Title -->
If you already solved [Prime Numbers Generation](./prime-numbers-generation) - here is an inverse version of it.

Given several pairs of primes (like `a, b`) you are to tell for each of them the total quantity of primes in the range
limited by these values (inclusive), i.e. such `p`-s that:

    isPrime(p) = true
	
		and
	
	a <= p <= b

**Input data:** will contain the amount of pairs in the first line.  
Next lines will contain one pair of primes each, the first value is always less than the second. All values will be less
than `3000000`.  
**Answer** should contain the quantity of primes in the ranges specified by these pairs.

Example:

     input data:
	 3
	 5 19
	 11 29
	 2 23
	 
	 answer:
	 6 6 9

*Hint: you may start with generation of the array (or list) of primes in ascending order. However you will need to
use some effective method for searching values in this list, otherwise your program would work significantly slower
than it should.*