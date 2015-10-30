_Thanks to [MoffSerge](../user_profile/moffserge) for suggesting this problem!_

Some primes are **Emirp**. This word is just `"prime"` reversed. Such primes if their decimal notation is
reversed give another prime value.

The number `13` for example have such a property - if we write down its digits in reverse order the resulting value
`31` also appears to be prime!

Among the two-digit primes here is even more interesting one: `37` if reversed becomes `73` and both of them are primes.
Moreover they are `12th` and `21st` primes (if we agree that `2` is the `1st`) and these two numbers also are each
other's mirror image. Though of course such coincidence is rare one and hard to check for large values.

Your goal is simple. For given `X` you are to find closest next **emirp** prime (i.e. value greater or equal to `X`
which is prime itself and its reverse in decimal notation is also a prime).

**Input data** will contain the amound of primes to find in the first line.  
Next lines will contain a single `X` each.  
**Answer** should contain closest **emirp** prime for each of `X`-s.

Example:

    input data:
	3
	10
	20
	50
	
	answer:
	11 31 71

_Values of `X` could be large enough so you may want to use some advanced primality test, perhaps non-deterministic one._
