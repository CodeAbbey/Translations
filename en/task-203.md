Do you know how AI for Chess or Checkers work? If not - here is an exercise just for you! Though we are
going to use simpler game of Tic-Tac-Toe to demonstrate the algorithm.

_We hope you are familiar with Tic-Tac-Toe game - otherwise you may want to try
[this problem](./tic-tac-toe) first. We also have a problem about playing [Connect Four](./connect-four)
game which also relies on "minimax"._

###Minimax Algorithm Explanation

So, how should program play the game like Chess or Tic-Tac-Toe (e.g. the game with "full information")?
The core idea is similar to how the human (grandmaster) plays:

- for given position think about every possible move;
- for each of moves try to assess the resulting position;
- choose the move which leads to the "best" position by assess.

So simple! But how to "assess" position? Let us agree that assessment is expressed as a single numeric
value, with `0` meaning that neither side is doing better, positive if the `first` player is winning
and negative if the `second` is winning.

For game like chess good assessment function could be built simply by counting remaining pieces (i.e.
white score `1` for pawn, `2.5` for knight, `3` for bishop etc and black score negative values respectively).

With Tic-Tac-Toe the matter is simpler. Let us score `1` for position where Crosses have won (i.e. have
three in a line) and `-1` for position where Noughts have won.

**Is it sufficient?**

No. If we check only all possible moves for one side, we will probably fail to find good solution.
For example with chess we probably will find that "best move" is to capture enemy's Knight with a Queen
but we miss that on the next move the opponent can recapture our Queen with a pawn.

For Tic-Tac-Toe it is quite possible that single move does not lead to win so we get `0`-s for every
move and have no idea what to choose.

So we shoud **go recursive**. Really, let us for every move of ours then check every possible response
of the opponent. Suppose that opponent will choose the best continuation for him (and the worst for us).

We can continue such recursive search for any number of moves in depth. However for chess usually
we limit this depth (otherwise it will be endless search) - while in Tic-Tac-Toe we really can explore
every variant to the end.

So that is how the algorithm should look in pseudocode:
	
	# 'side' is either 1 or -1 (for 1-st and 2-nd player respectively)
	
    function assess(side):
		if some side have won:
			return this side
		endif
		
	    bestMove = null
		bestValue = -1000000
		
		for each (move from allPossibleMoves):
		    makeMove(move)
			value = assess(-side)
			takeBack(move)
			
			if value * side > bestValue:
			    bestValue = value * side
				bestMove = move
			endif
		endfor
		
		return bestValue * side

We leave it up to you to understand how it works in details (according to explanations above) and
implement it yourself for Tic-Tac-Toe game.

###Problem Statement

You will be given several positions in Tic-Tac-Toe game (defined by the sequence of first moves) -
and you are to calculate assessments for every possible move. We will mark moves with cell indices
in range `0..8` of the cells as in this diagram:

	     |     |
      0  |  1  |  2
	     |     |
    -----+-----+-----
	     |     |
      3  |  4  |  5				(cell_index = Y * 3 + X)
	     |     |
    -----+-----+-----
	     |     |
      6  |  7  |  8
	     |     |

So that sequence of moves `4 0 2` for example means that firstly `X`-s is put into central cell,
then `O` goes into upper-left corner and next `X` - into the upper right corner. We agree that
`X`-s always start the game.

**Input data** will contain the number of test-cases in the first line.  
Next lines will contain sequences of moves for each test case (starting from the empty board each time).  
**Answer** should tell for each position the assessments of moves to every of `9` cells. Assessments
should be expressed as digits `0`, `1` or `2`. Of them `2` means that side to move (either `X` or `O`)
will win if it puts its mark to given cell, `1` means that draw could be secured and `0` means that
either this cell is already not-empty, or move to it allows the opponent to win the game. Digits
should be written without spaces, e.g. `010102000` means that move to cell `1` or `3` leads to draw
and move to cell `5` leads to victory.

Of course phrases "side will win", "side will secure a draw" or "opponent will win" assume that both
sides make further moves in optimal way.

Example:

	input data:
	3
	1 8 7
	7 1 5 3 4 8
	7 2 1 3
	
	answer:
	000020000 101000100 000021202

Let us analyse these cases.

**1-st case:**

    - X -
	- - -
	- X 0

Now it is the move for `O`-s. Obviously if they will not take the central cell (`# 4`) the crosses
then can win on the very next move. That is why assessment for every cell except `4` is `0`. But
if Noughts will go this way, the crossess are forced to go to cell `0` and the noughts make a
fork putting their mark into cell `2`, thus gaining a victory.

**2-nd case:**

    - 0 -
	0 X X
	- X 0

Here we simply have just `3` possible moves - and after any of them neither of sides can win -
really we have to put two more `X`-s and one more `O` - but there is no way to put them so any of
them make a line of three.

**3-rd case:**

    - X 0
	0 - -
	- X -

Now `X`-s are to move. If they go to cell `0`, then opponent takes center with a fork, so it is
a way to lose the game.

Putting the mark into cell `4` makes immediate win, while going to `6` or `8` leaves the fork against
noughts, so all these moves win.

At last, if we put `X` to cell `5` then `O`-s will take the center and the rest of the game is
forced (`X` to `6`, then `O` to `8` and `X` to `0`) making a draw.
