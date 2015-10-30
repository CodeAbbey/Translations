<!-- #Paths in the Grid -->
Dynamic Programming is an approach for solving problems very popular among competitive programmers and problemsetters
at the resources like [TopCoder](http://topcoder.com/tc). Very common example which should be learned is counting
number of paths through rectangular grid (for example, districts of the city etc).

Imagine a map of a swamped ground represented by a rectangular grid:

    @ + + + +
    + + + X X
    + X + + +
    + + + X +
	+ X + + X
	+ + + + $

where `X` depicts a pit (an impassable square, where person will be certainly drowned) while `+` are safe patches.

A **hero** should travel from upper left corner (marked with `@`) to lower right corner (marked with `$`). He only can
move by safe squares, and from each square he only can move in two directions - either **right** or **down**
(as seen on a map). I.e. backward movements are forbidden - our hero could not waste time due to the lack of food in
his knapsack.

We are interested in how many **different** paths there exist from one corner to another under given rules.

**Input data** will contain number of rows and columns of the field in the first line - `M` and `N`.  
Then the field itself will come in `M` lines, each of which contains `N` characters separated by spaces.
Impassable squares are marked with `X` symbols.  
**Answer** should contain the only number - the number of existing paths.

It is guaranteed that the result does not exceed `2,000,000,000`.  
However, it could happen that there is no any path at all.

Example:

    input data:
	6 5
    @ + + + +
    + + + X X
    + X + + +
    + + + X +
	+ X + + X
	+ + + + $
	
	answer:
	9

At **ProjectEuler** site there is a version of the same puzzle without obstacles:
[Lattice Paths](http://projecteuler.net/problem=15) - you are recommended think of it if you have no idea at first.