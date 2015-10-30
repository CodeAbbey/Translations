Supposing you are already acquainted with [Combinations](./combinations-counting) let us write a program for generating
and enumerating them in order.

We'll use sets of up to `36` elements and for simplicity they are marked with digits of numeral system with base of `36`:

    0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

Obviously, combinations could be ordered lexicographically. For example for combinations of `3` elements chosen from
the set of (`0 1 2 3 4`) - i.e. `C(5,3)` we have the following `10` possible combinations, sorted in ascending order:

    0:   0 1 2
	1:   0 1 3
	2:   0 1 4
	3:   0 2 3
	4:   0 2 4
	5:   0 3 4
	6:   1 2 3
	7:   1 2 4
	8:   1 3 4
	9:   2 3 4

You can easily write a simple algorithm from this example - like recursively increasing rightmost value, then
one preceeding it etc. However it is not quite fast and you may want to find some optimization for it.

###Problem statement

Write a program which for given `N`, `K` and `I` will produce `I`-th combination of `K` elements from `N`.

**Input data** will contain the amount of testcases in the first line.  
Following lines will have single test-case each, formed of three values `N`, `K` and `I` with the following
limits:  `N <= 36`, `K <= N`, `0 < I < C(N,K)`.  
**Answer** should give the required combinations.

Example:

    input data:
	3
	5 3 2
	30 15 0
	36 16 7307872109
	
	answer:
	014 0123456789ABCDE KLMNOPQRSTUVWXYZ
