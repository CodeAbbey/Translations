This problem is similar to [Enumerating Combinations](./enumerating-combinations), however there is minor but significant
difference.

We again are interested in building combinations of `K` elements of the given set of size `N`. However, some elements
within the set could be duplicated. Let's call it **Combinations with limited repetitions**. For example think of the set:

    0 1 1 2 3

If we try to build combinations of `3` elements, we'll found that instead of `10` only the following `7` will do:

    011 012 013 023 112 113 123

**Input data** contain the value `K` and the set of elements (digits from `0` to `9`) in form "`K` of `X Y ... Z`".  
**Answer** should contain all possible combinations in lexicographic order.

Example:

    input data:
	3 of 0 1 1 2 3 3 3 4
	
	answer:
	011 012 013 014 023 024 033 034 112 113 114 123 124 133 134 233 234 333 334

*Note: you may expect that there would be from `200` to `1000` results.*