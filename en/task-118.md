<div style="text-align:center">
<canvas id="demo" width="300" height="250" style="border:5px solid #888;border-radius: 5px;background: black;" onclick="clickMove(event)"></canvas>
<form>
	<label>Puzzle #: </label>
	<input id="input" type="text" title="Input Puzzle Number" value="0"/>
	<input type="button" value="Restart" onclick="setvals()"/>
</form>
<div class="hint">Click numbers inside rectangle to make a move</div>
</div>

Once upon a time there was a computer game called [Maxit](http://www.myabandonware.com/game/maxit-10). It was just
beginning of the IBM-PC era, so the game is older than average user of CodeAbbey. Later ports included version
called "Hot Numbers" with pictures by Penthouse (amiga version) - we'll not share the link here! :)

The gameplay (for two players) is simple:

- the square field is filled randomly with negative and positive numbers;
- some cell is chosen as "current" and is empty;
- the first player on his move can choose any cell in the same row as current - he erases the value here and adds it
	to his score - the chosen cell becames "current" then;
- the second player on his move can choose any cel in the same column as current in the same way and tries to increase
	his score;
- positive values increase player's score, while negative ones decrease it;
- cells from which numbers were already taken could not be visited again by any of the players;
- the game ends when one of the player's could not make a move (because of empty current row or column) - then the
	scores of the players are compared, one who gained more - wins.

In your free time you can try programming **AI** for this game - it is a good exercise since it is almost direct
implementation of [Minimax algorithm](http://en.wikipedia.org/wiki/Minimax), allowing all of its features without
additional complexity given by specific rules of chess, checkers etc.

###Single-player modification

We'll use the following modifiation: there is only one player, and he performs "horizontal" and "vertical" moves in
turns. On "horizontal" move he adds the taken value to his score while on "vertical" move he subtracts it.

The goal is to maximize score.

Try playing the small demo above to get the idea of the rules. You will see that different sequences of moves lead
to different result, for example imagine the situation of half-empty board of size `3x3`:

    -3 :: +5
	@@ :: ::
	-2 :: -1

Here `@@` marks the current position, `::` represents empty squares and the next turn is "vertical".

Player can choose to take `-2` or `-3` - then remaining moves would be pre-determined. If he choses `-2` he has
the following chain of score change:

    sub -2
	add -1
	sub +5
	add -3
	------
	    -7

If instead he choses `-3` then his fate is completely different:

    sub -3
	add +5
	sub -1
	add -2
	------
	    +7

If the field has one extra value `-1`, like this:

    -3 :: +5
	@@ :: -1
	-2 :: -1

Then player can prefer to take it on the `3rd` move to end the game before clearing the whole board with `+9` score
(because there would be no more values in the middle row and no move could be made).

###Problem statement

You will be given large square field and your goal is to get maximum score of it following the rules described above.
As an answer you'll need to return the sequence of moves. Each move should be represented by a single value - the
index of the cell in the current row or current column, `0`-based.

**Input data** will contain the size of the field in the first line.  
Then the field itself will follow, rows are numbered from the top and columns from the left.  
`0` will mark the starting position of the "current" cell.  
**Answer** should contain the sequence of moves.

Example:

	input data:
	4
	 0 -3 +4 +3
	-3 +4 -2 -1
	+2 -1 -4 +3
	-3 -1 -1 -2
	
	answer:
	2 2 0 1 1 0 3 3 2 1 3 2 1 3 0

*This sequence of moves will lead to score of `19`, though you can do better!*

**Challenge result** is assessed by the following formula:

    score = score_gained_by_user()
	max = 51000
	min = 46000
	result = (score - min) / (max - min)

<script src="http://codeabbey.github.io/maxit-single-player/maxit.js"></script>