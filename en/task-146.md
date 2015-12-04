<div style="text-align:center">
	<span class="hint">Click the areas of the same colors to remove them. Try to achieve maximum points!</span><br/>
    <label>Score: <input type="text" disabled="true" value="0" id="score" size="7" class="centered strong"/></label><br/>
    <canvas id="demo" width="600" height="400" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
    <br/>
    <label>Seed: <input type="text" value="0" id="seed" size="5" style="text-align:center"/></label>
    <input type="button" onclick="colorBlocks.reset()" value="Reset"/>
</div>

<script src="http://rodiongork.github.io/ColorBlocksJs/canvashelper.js"></script>
<script src="http://rodiongork.github.io/ColorBlocksJs/colorblocks.js"></script>
<script>
window.onload = function() {
	colorBlocks = new ColorBlocks();
}
</script>

###Game rules

_After this exercise was added I've been hinted that the game is known as
[Same Game](http://en.wikipedia.org/wiki/SameGame) originating back in `1985` - it is almost "ancient"!_

This is a well-known game: the box is filled with the cubes of different colors and player can remove groups of the
same colors consisting of blocks with their sides touching each other. After each move the cubes above the empty
area fall down because of gravity. When the whole column is cleared it collapses (blocks on the right are moved
leftwards to close the gap). For example:

    1 2 3 2     1 - - 2     1 - 2 -
	1 3[4]2     1 2 - 2     1 - 2 -
	2 4 4 1     2 3[3]1     2 2 1 -
	1 2 3 2     1 2 3 2     1 2 2 -

From initial position player chooses to remove `4` at the position `2,2` (with `0,0` at **leftmost bottom**) and two
additional `4`-s below it are removed, then `2`, `3` and `3` from above fall down. At the next move player removes
`3` at the position `2,1` and two neighboring `3`-s are removed also, so `2` falls down and the rightmost column shifts
to the left to close the gap.

The game continues until all cubes are removed.

###Scoring

Player gains `1` point for removing group of a single cube. Group of two cubes costs `3` points, while group of three
costs `6` and so on, with the formula

    score = count * (count + 1) / 2

i.e. progression is one of **triangular** numbers.

---

###Problem statement

Your goal is by the given initial position and sequence of moves to tell the final score of the game.

Try to play with the demo above to get better understanding of rules and scoring.

**Input data** will contain:

- a line with the size of the field `N`(i.e. you are to deal with the square box of `N*N` dimension);
- `N` lines of `N` digits (color indices) each representing the game field (or the box);
- a line with the count of moves `K` described below;
- a line with `K` pairs `Xi` and `Yi` (separated with comma-and-space) - zero-based coordinates of moves
	(where `Y=0` is the bottom line and `X=0` is the leftmost column).

**Answer** should contain a single value - the final score.

Example:

	input data:
	5
	14111
	23334
	43212
	33323
	21232
	12
	0 4, 3 0, 0 1, 2 2, 1 1, 4 2, 3 2, 0 1, 3 2, 3 1, 3 0, 2 0
	
	answer:
	54
