_Please refer to article [interactive problems](../wiki/interactive-problems) about technical aspects of this exercise._

Now you are to play **Nim** game against a server. The rules are very simple:

- there are `3` heaps of stones - both players know amounts in each of them precisely;
- players pick stones in turns - it is allowed to take any number of stones from any single heap;
- the one who grabs the last stone(s) is a winner.

For example, if there are `3`, `4`, and `5` stones in heaps `#0`, `#1` and `#2` respectively, and players do the
following moves:

	Player 1			Player 2				Stones remain
	--------			--------				-------------
	3 from #2									3  4  2
						2 from #1				3  2  2
	3 from #0									0  2  2
						2 from #1				0  0  2
	2 from #2									0  0  0

And the first player is a winner.

---

###Technical details

Server endpoint is at [http://codeabbey.sourceforge.net/nim-game.php](http://codeabbey.sourceforge.net/nim-game.php)

After you start the game, server will return sizes of heaps with its answer.

Then you make each move by specifying `H` (the number of heap to take from) and `S` (amount of stones to take) in a
single line marked with `move`.

Server then answers with its move in the same format and also with updated state of the heaps.

The end of game is signalized when server after its move detects that either `2` or `3` heaps are empty. In the first
case it is your victory, in the second you lose the game.

**Time limit** is `10` seconds per move. So you may try to play in self-manual mode :)

**Input data** will have authentication token and **Answer** should contain victory token on submit.

Example:

	YOU									SERVER
	------------------------			------------------------
	
	token: <your-token>					heaps: 3 4 5 							// request-response # 1
	
	token: <your-token>					move: 1 2								// request-response # 2
	move: 2 3							heaps: 3 2 2
	
	token: <your-token>					move: 1 2								// request-response # 3
	move: 0 3							heaps: 0 0 2
										end: <your-victory-token>	
