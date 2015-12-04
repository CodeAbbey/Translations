<!-- #Title -->
*You may refer to [Fibonacci Sequence](./fibonacci-sequence) task if you are unfamiliar with the subject.*

Given usual Fibonacci Sequence, starting with `0` and `1`:

    0 1 1 2 3 5 8 13 21 34 ...

and some value `M` you will be asked to find the index of the first non-zero member of this list, which is evenly divisible by
this `M`, e.g. if you are given `M = 17` the answer is `9` (the index of the element `34`).

**Input data** in the first line will contain the number of test-cases.  
Next line will contain exactly this of divisors `M` (not exceeding `10000`) for which you should give answers.  
**Answer** should contain indices of members of Fibonacci Sequence, separated by spaces.

Example:

    input data:
	3
	17 12 61
	
	answer:
	9 12 15
