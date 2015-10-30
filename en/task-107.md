This is a famous problem - one of the first scientist to study it was Leonard Euler himself!

**Given a chessboard and a single Knight piece find such a way for the Knight that all squares are visited, but each
of them only once.**

If you are not well acquainted with the chess rules you only need to know that the Knight makes moves resembling the
shape of the letter `L` it either goes two squares horizontally and then one vertically or on contrary two squares
vertically and one horizontally. So in the best case it can make `8` different moves from the given cell:

    8 | - - - - - - - -
    7 | - - - - - - - -
    6 | - - 2 - 1 - - -
    5 | - 3 - - - 0 - -
    4 | - - - N - - - -   N - depicts the Knight's initial position here
    3 | - 4 - - - 7 - -   and digits - landing squares for 8 different jumps
    2 | - - 5 - 6 - - -
    1 | - - - - - - - -
	  +-----------------
		a b c d e f g

So the problem of visiting all the squares with such jumps is related to [Travelling Salesman](./travelling-salesman)
problem, however there we need no optimization, we only need to reach the end. The problem is usually solved simply
by depth-first-search, however on larger boards some heuristics could be useful to save the time. One of the best
known is the **Warnsdorff's rule** - the knight should first explore the cells from which there are less "exits" than
from others.

I.e. for example if at some point Knight can go either to the cell with `5` ways out or to the cell with only `2` -
then obviously the latter variant should be tried first.

###Problem Statement

You will be given large enough rectangular board with a single square removed from it (to make things bit more random)
- and your goal is to find any path by which the Knight can visit all remaining squares.

**Input data** will contain two integers af the first line - height `M` and width `N` of the board.  
Next line will contain two more integers - coordinates (`X` and `Y` - both `0`-based) of the removed square.  
**Answer** should contain coordinates of the starting square (also `0`-based) which you can choose arbitrarily and
then directions of `M*N-2` jumps as integers from `0` to `7`, just like at the diagram above.

Example:

    input data:
	3 4
	3 2
	
	answer:
	0 0 0 3 6 0 3 6 3 0 6 3
	
Let us draw this example:

    2 | c f i #
    1 | h k b e
    0 | a d g j
	  +---------
	    0 1 2 3

Here we start from the square with coordinates `(0, 0)` so it is marked with letter `a`, then we jump to `b` and it
gives us direction `0`, next cell is `c` with direction (from `b`) of `3` and so on. The top-right corner with
coordinates of `(3, 2)` is removed and the Knight should not visit it.
