Famous programming problem of **Packing the Knapsack** have several variants. The general statement is like following:

**Given a set of items, each of which have some `Weight` and `Value`, we want to select some of them to pack into
the knapsack which has limit of `Maximum-Weight`. The goal of selection is to maximize the `Total-Value` of packet items.**

It is told that the problem have a number of appications in transportation, logistics etc - think of building the train
of railway cars (with varying content and cost), loading ships with containers or aircrafts with boxes, parcels -
besides this it could be the part of more complex algorithms in networking, data transferring software etc.

Three common variants of the problem are:

1. **Unbounded knapsack** - when items of each kind are presented in unlimited amount.
2. **Bounded knapsack** - each type of item is presented in several copies (we know amount for each type).
3. **0/1 knapsack** - there is a single copy of each type of item, so any type/item could be either included (`1`) or not (`0`).

The last of three is the most popular and so we'll try to solve this. If the weights of the items are given with
arbitrary **real** numbers, the problem can not be solved efficiently. However with integer weights we can use
**dynamic programming** approach, increasing weight by iterations.

###Algorithm

Trivial approach would be to try all combinations of items. There are `2^N` of them and it will work for about `20`
items in several seconds. However for larger values we are to use dynamic programming.

Suppose we have a set of items, labeled with numbers from `1` to `N`. Each of them has the known weight `w[i]` and
the value `v[i]`.

Let us iterate through these items and on each
iteration examine all possible weight limits `W` from `0` to `Wmax` (capacity of knapsack) and try to find the
answer for the given `W` and subset of items from `1` to `i`:

    FOR i IN 1..N
	    FOR w IN 0..Wmax
		    subset = items from 1 to i
		    solve_knapsack(subset, w)
		END FOR
	END FOR
	
	result = solve_knapsack(items from 1 to N, Wmax)

Here `solve_knapsack` function returns the value of selected items (for given set and weight limit) and could be
performed in a single choice, using previously calculated values.
Really, for `i-th` element we could either include it or not.

- if we do not include it, the total value would be the same as for items from `1` to `i-1`, and the same limit weight `w`;
- otherwise, the total value would be the same as for items from `1` to `i-1` and limit weight `w-w[i]` (current
	limit reduced by the weight of item being added) plus the value of the current element `v[i]` since it is added.

We only need to choose which value is greater. It will look like:

    FUNCTION solve_knapsack(items from 1 to i, weight_limit)
	    valueNo = solve_knapsack(items from 1 to i-1, weight_limit)
		IF weight_limit < w[i] THEN
		    return valueNo    # we can't add current item anyway
		END IF
		valueYes = solve_knapsack(items from 1 to i-1, weight_limit - w[i]) + v[i]
		return max(valueYes, valueNo)
	END FUNCTION

If we will store previous results given by `solve_knapsack` in array (or rectangular matrix since there are two
parameters) we got the DP algorithm. Note that internal "call" to `solve_knapsack` can be performed with such a
pair of parameters for which calculation has never taken place before - we should return `0` for such cases.

###Problem statement

You are given a set of items - their weights and values. Also you are told the maximum total weight (capacity of
the knapsack). Return the maximum possible value of chosen items.

**Input data** will contain amount of items `N` on the first line.  
Next line will have the maximum allowed capacity `Wmax` of the knapsack.  
Then there would be `N` lines each with two values - `w[i]` and `v[i]`.  
**Answer** should have a single value - maximum posible value of items placed into knapsack.

Example:

	input data:
	7
	86
	5 8
	15 20
	13 25
	15 31
	28 65
	8 14
	23 57
	
	answer:
	186

Here items with values `8`, `25`, `31`, `65` and `57` are choosen with total weight of `84`.
