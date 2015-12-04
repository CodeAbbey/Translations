Recently I've been interviewed for some job position. To my surprise I was asked to sit at the computer and modify
an existing program. The program performs tracking for chess game - i.e. moving pieces on the board according to given
list of moves and printing out the resultant position.

I was required to add functionality to check the correctness of pawn moves and rotation of sides between moves (i.e. that
none of players make two moves at once).

Those who are acquainted with `Java` (and have some idea of using `JUnit`, `maven` and `github` can amuse themselves
with [the full version of this task](https://github.com/rodiongork/ChessInterview), as
it was proposed to me (I only made some minor changes and translation).

For others here is the adaptation of the task.

----

###Problem Statement

You are to track the sequence of moves in [Chess](http://en.wikipedia.org/wiki/Chess) game and check the validity of
the pawn moves (other moves are considered correct). As an answer print the number of the incorrect move.

The game is each time started from the initial position:

      +-----------------+
	8 | r n b q k b n r |
	7 | p p p p p p p p |
	6 | - - - - - - - - |
	5 | - - - - - - - - |
	4 | - - - - - - - - |
	3 | - - - - - - - - |
	2 | P P P P P P P P |
	1 | R N B Q K B N R |
	  +-----------------+
        a b c d e f g h

As you see we denote:

- `white` pieces with uppercase letters (`P N B R Q K`) and `black` with lowercase (`p n b r q k`);
- pawn with `P`, kNight with `N`, bishop with `B`, rook with `R`, queen with `Q` and king with `K`;
- rows with numbers from `1` to `8` and columns with letters from `a` to `h`.

The move of a piece is described by its starting and ending coordinate, for example:

- `e2e4` - white pawn from `e2` goes to `e4`;
- `g8f6` - black knight from `g8` jumps to `f6`;
- `d1h5` - white queen from `d1` travels to `h5` (very stupid move though correct);
- `f6h5` - black knight from `f6` captures the white queen at `h5`.

After these four moves the position will look like following:

      +-----------------+
	8 | r n b q k b - r |
	7 | p p p p p p p p |
	6 | - - - - - - - - |
	5 | - - - - - - - n |
	4 | - - - - P - - - |
	3 | - - - - - - - - |
	2 | P P P P - P P P |
	1 | R N B - K B N R |
	  +-----------------+
        a b c d e f g h

###Pawn move rules

You should check the moves of pawns according to following set of rules:

- pawns move only forward, `white` go from the row `2` up and `black` go from the row `7` down;
- if pawn does not capture anything, it moves straight forward by the same column;
- pawn advances exactly one row per move, except the first move when it can optionally go two squares forward (e.g.
    `e2e4` for white or `d7d5` for black);
- pawn could not move forward if the path is blocked by any piece;
- capture is performed by forward diagonal jump by one square to the adjacent column (e.g. `e4d5` for white or `c7b6`
    for black) - of course the landing square should be occupied by the enemy piece which is captured.

We do not regard or check the three special cases: the capture "en passant", the promotion of the pawn to other piece
at the last row, the move which opens attack on the king or does not remove an existing one (it is illegal).

----

**Input data** will contain the number of testcases in the first line.  
Next lines will contain one testcase - i.e. one sequence of moves to be checked - each. Of course each sequence should
be started from initial position.  
**Answer** should for each sequence tell the number of first incorrect move (starting from `1`) or `0` if the whole
sequence is valid. Separate answers for different test-cases with spaces.

Example:

    input data:
	3
	b2b3 b8c6 c2c4 c7c5
	e2e4 g8f6 d1h5 f6h5
	d2d4 e7e5 g1f3 e5d4 c2d4 d8e7
	
	answer:
	4 0 5
