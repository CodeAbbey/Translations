Have you ever played [2048 Game](http://gabrielecirulli.github.io/2048/)? If no, then probably it is worth trying :)

Many programmers spend many hours on this (both instead of work and instead of sleep). However, though it is addictive
enough it is still simple to code. And now we are going to try - and try to invent solution which does not look too
clumsy.

You will be given a `4-by-4` field randomly covered with values `2` and `4` along with the sequence of player moves,
specified with letters `U` for "up", `D` for "down", `L` for "left" and `R` for "right".

At each move all numbers at the field start sliding in a given direction and if two "tiles" with the same values are
"pressed" against each other by this move, they combine producing a single tile with the sum value. Of course this frees
one square of the board.

In case when more than `2` tiles with same numbers are so "pressing" in one line, firstly two "front" are combined,
i.e. if moving "down" and we have `3` similar tiles in column, two lowest are joined.

For example:

    initial         D            R            D
	
	2 2 4 2      - - - -      - - - -      - - - -
	4 2 2 4      2 2 4 2      - 4 4 2      - - 4 2
	2 2 2 2      4 4 2 4      - 8 2 4      - 4 2 4
	2 4 2 2      4 4 4 4      - - 8 8      - 8 8 8

Here three steps after initial position are shown - "down", "right" and "down". As you can see the last move joins
nothing, only aligns tiles against the edge of the field.

**Input data** will contain initial setup - `4` lines of `4` values each.  
The `5-th` line will contain the sequence of moves.  
**Answer** should contain the counts of tiles of each kind after these moves, in order - i.e. first the amount of
`2`-s, then amount of `4`-s etc.

Example:

	input data:
    2 2 4 2
	4 2 2 4
	2 2 2 2
	2 4 2 2
	D R D L U
	
	answer:
	0 2 2 1

*Note: here the amount of `2`-s is zero and amount of `32`-s and greater tiles too - but you should omit spare zeroes
on the right.*