In the [Knapsack of Integers](./knapsack-of-integers) we have learnt how to calculate the maximum value of items which
could be collected in a knapsack with limited total weight.

But what should be these items? The algorithm, as it was described, does not return their indices!

So here is an evolution of the task. Write the same program, but extend it in such a way that the indices of the
chosen items are returned. Solution should not be greatly changed - you only need to **backtrack** through the
matrix which stores the intermediate results of your dynamic programming approach - from `dp[Wmax][N]` to zero.

*Hint: You can prefer to add some flags to matrix values while calculating it - but it is not necessary.*

**Input data** will contain amount of items `N` on the first line.  
Next line will have the maximum allowed capacity `Wmax` of the knapsack.  
Then there would be `N` lines each with two values - `w[i]` and `v[i]`.  
**Answer** should have a list of indices - `0`-based labels of items to be placed into knapsack. You may output them
in any order and if several solutions are possible - any will do.

Example:

    input data:
	6
	58
	11 29
	18 48
	25 75
	15 43
	26 42
	29 82
	
	answer:
	1 2 3

Here the answer tells us to choose the items with total weight `18 + 25 + 15 = 58` and value `48 + 75 + 43 = 166`.
