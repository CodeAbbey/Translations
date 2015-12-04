_This game have been puzzling me for about dozen years. Recently I encountered one of its variation once again -
it was given as a part of exam for to-be-interns by some software corporation._

It is played between two participants. They lay several objects (matchsticks, little stones, coins) in a single line.
This line can have several spaces, for example:

    | | |    | | | |    | |

Here are three groups, containing `3`, `4` and `2` sticks. At each move the player can take any `1` or `2` adjacent
sticks (it is forbidden to take `2` sticks belonging to different groups). Of course some of the groups can split
into smaller one after the move.

The person who is forsed to take the last stick - loses.

For example, the position shown above can evolve as following:

    | | |    | | | |    - |			player A took 1 stick from the last group of 2
	
	| | |    | - - |      |         player B took 2 sticks from the middle group of 4 (splitting it)
	
	| - |    |     |      |         player A took 1 stick from the middle of group of 3

After this move there are `5` separated sticks so any further moves would consist of taking a single stick - e.g.
player `B` loses the game.

Obviously for each position it is predetermined whether it is `losing` or `winning` if both players keep optimal
strategy. For example in this case player `B` could probably win if after the first move of `A` he would take `2`
sticks from the first group, reducing position to `1 4 1` instead of `3 1 1 1`. Is it correct? Can you prove it?

**Input data:** will provide the number of testcases in the first line.  
Next lines will contain a single test-case each - specifying a sequence of groups of (initially) adjacent sticks,
e.g. `3 4 2` for the starting position proposed above.  
There will be no groups larger than `7` sticks and average quantity of groups will be about `10`.  
**Answer:** should contain for each position either `1` if it is `winning` or `0` otherwise.

Example:

    7
	1
	1 1
	1 1 1
	4
	2 2
	3 3
	1 4
	
	0 1 0 0 0 0 1

_We call position `winning` if the first person to move can win if playing optimally and `losing` otherwise._