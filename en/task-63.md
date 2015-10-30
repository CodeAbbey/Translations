<!-- #Title -->
Fundamental Theorem of Arithmetic states that **any integer could be represented as product of one or more primes and
such representation is unique**, for example:

    1000 = 2 * 2 * 2 * 5 * 5 * 5
	1001 = 7 * 11 * 13
	1002 = 2 * 3 * 167
	1003 = 17 * 59
	1009 = 1009
	
*Here we regard `1009` as a singular case of product of only one prime value - itself!*

It is still unknown whether factorization could be done efficiently, i.e. fast enough for big numbers. For example a
number built as product of two `200`-digit primes (i.e. having only `400` digits itself) will require many thousand
years to decompose it back into original pair of primes on modern computers.

Of course this precious fact has great significance in cryptography. If fast algorithm is ever found, many crypting
methods popular nowadays will become insecure at once! The classic example is an **RSA** algorithm of which you can
learn more from the [dedicated exercise](./rsa-cryptography) and other linked tasks.

###Problem Statement

You will be given several numbers (not very large, so do not be afraid) to decompose them into products of primes.

**Input data** will contain amount of integers to factorize in the first line.  
Next lines will contain one integer each (not exceeding `13` digits in length).  
**Answer** should contain product representation for each of these integers, written like `p1*p2*p3` where `p1 ... p3`
are some primes **sorted** in non-decreasing order. Products should be separated with spaces.

Example:

    input data:
	5
	1000
	1001
	1002
	1003
	1009
	
	answer:
	2*2*2*5*5*5 7*11*13 2*3*167 17*59 1009
