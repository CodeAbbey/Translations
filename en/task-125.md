*This problem was suggested by [Erik Kvanli](../user_profile/erikkvanli) - thanks a lot!*

This sorting algorithm is never used in production. Rather it was proposed as both programmer's joke and the case for
exercise and study.

[Bogosort](http://en.wikipedia.org/wiki/Bogosort) works by shuffling of the array and checking, whether it by chance
appeared in the proper order. This is repeated as many times as necessary. The expected number of iterations to
succeed grows dramatically with the increase of the array size. But one special property of the algorithm is
that its **worst-case** time complexity is **unbounded** - it may never stop in some cases.

You are to implement the algorithm following directions below and tell the amount of iterations it took (or report the
cases when it will never end).

###Randomizer

We'll use random number generator similar to [Neumann's](neumanns-random-generator) with a small modification:

- generated values have `6`-digit with, probably, some leading zeroes;
- given current value `X` split it into two parts of `3` digits and swap these parts to get auxiliary value `Y`
	(i.e. if `X=654321` then `Y=321654`);
- multiply `X` by `Y` to get `12`-digit value (probably with some leading zeroes);
- cut the middle `6` digits from this long number to get next value for `X`.

For example starting from `X=654321` we get the following sequence:

	654321 464966 372900 748718 139565 873624 904049 115661
		465222 495612 559871 960608 971847 98072 70795 286980 ...

###Shuffling

Given an array use the approach proposed in the [Cards Shuffling](./cards-shuffling) task to toss it randomly:

    A - is an array
	N - is its size
	
	FOR i = 0 ... N-1
	    r = next random value from randomizer
		j = r % N
		SWAP A[i] with A[j]
	END FOR

Use the value `918255` to initialize randomizer. **Note** that the first value returned is not the seed - rather it
is the following one!

At each next iteration apply shuffling to the result of previous iteration rather than to initial state of array.

For example, if the array contains values `1 2 3 4 5 6 7` initially and randomizer is seeded with `654321` then
after a single shuffling loop the order should change to `3 4 1 5 7 2 6` - the following sequence of swaps is
performed:

    0-5  1-3  2-5  3-6  4-3  5-6  6-0   # each pair describes i-j indices

###Input and Output details

**Input data** will contain the number of test-cases in the first line.  
Each testcase given in separate line will contain an array of exactly `7` values.  
**Answer** should contain the amount of shuffles needed to sort the given array or `-1` if it will never be sorted.

Example:

	input data:
	4
	61 91 35 135 105 120 161
	156 30 119 99 81 60 137
	102 170 142 55 117 83 26
	102 81 128 168 56 145 27
	
	answer:
	-1 156 -1 1391

**Note:** random generator should be reinitialized for each test!