_Idea for this puzzle was proposed by [Gaurav Kamath aka Moriarty](../user_profile/gauravkamath108) - thanks a lot!  
Note that it is really more about efficient data structure and algorithm rather than about math..._

Look at the integer `997739719` - it has a funny property - any substring of `3` digits i.e.:

    997739719
	---------
	997
	 977
	  773
	   739
	    397
		 971
		  719

any of these `997`, `977`, ..., `719` is a prime!

Such numbers built of chains of primes could be long enough, and they could be built using primes of more than `3` digits.  
Of course it is important that **prime substrings should be unique** - since otherwise we can generate endless
integers like `997399739...` and so on.

For example let us search for integers built of `5`-digit primes. Note that resulting chain could start with leading
zeroes, like this:

    0000233331793979193911399793199139313339119333773

since `00002` is a valid prime number too.

You will be given **hashes** of several such prime-chain-integers - and your task is to print these integers themselves.
Since we are interested in long enough integers, please ignore any of them with length less than `48` digits
(leading zeroes included).

###Hash Calculation

We'll use the following simple algorithm to calculate the hash of a long `NUMBER`:

    HASH = 0
	for D in digits(NUMBER):
		HASH = (HASH * 13 + D) % 100000007
	return HASH

where `D` are decimal digits picked from the `NUMBER` in order "left-to-right". For example the hash of the value
`000233...333773` shown above is `34475206`.

---

###Input and Output

**Input data** contain the amount of numbers to search for.  
Next lines contain a single hash value each.  
**Answer** should contain long prime-chain-number (of the length `48` digits or more) corresponding to each hash.

Example:

    input data:
	3
	34475206
	90962736
	39728928
	
	0000233331793979193911399793199139313339119333773
		749031379939791939113997931991393133317939371999719
			461031379939791939113997931991393133317939371999719

_Values here are placed into separate lines since they are just too long to fit a single line! However you should
simply separate them with spaces._
