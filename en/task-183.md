<div class="centered">
<img alt="Gameplay of Connect Four, animated" src="http://s14.postimg.org/52gsohv75/Connect_Four.gif"/>
<div class="hint">Animated example of gameplay (<a href="https://en.wikipedia.org/wiki/File:Connect_Four.gif">from wiki</a>)</div>
</div>

This game is similar to Tic-Tac-Toe, however the board is larger, but amount of possible moves is limited.

Imagine that the board is set vertically (rather than laying flat), and each player at his turn can put his mark
only on the top of any columns. In "physical" version color discs are simply dropped from the top.

The goal is to make the line of `4` or more marks - horizontal, vertical or diagonal. Original game field is `7x6`
(with `7` columns). We will use larger field of `9x8`.

**Now you will try to beat me in this game!**  
Since we all are programmers, your goal is to write a program which
can win against my program. Read more about [interactive-problems](../wiki/interactive-problems) if necessary.

Here is the link to game server:  
[http://codeabbey.sourceforge.net/connect4.php](http://codeabbey.sourceforge.net/connect4.php)

At each turn except the initial you need to send your move represented by the number of column to which you drop
your mark (from `0` to `8`). Server will respond with its move in the same manner.

Besides this current state of the board is shown to you in the following format:

- there are `9` sequences of digits corresponding to `9` columns, separated with spaces;
- if the column is empty, sequence contains the only digit `0`;
- otherwise it is built of digits `1` (for your marks) and `2` for opponents, upwards from the bottom.

For example the line `0 0 1 0 22 1121 0 0 2` describes the following field:

    - - - - - - - - -
    - - - - - - - - -
    - - - - - - - - -
    - - - - - - - - -
    - - - - - 1 - - -
    - - - - - 2 - - -
    - - - - 2 1 - - -
    - - 1 - 2 1 - - 2

To randomize the game, we start it not from empty field, but with **two marks** (one for each player) already
dropped randomly. You are always the player who makes the **first move**.
You should make each next move in **no more
than `5` seconds**.

You may **[watch this visualization](http://scvfast.com/playground/connect4.php)** kindly created for us by our
colleague [Bloggermark](http://www.codeabbey.com/index/user_profile/bloggermark) to understand the game better.

**Input data** gives you a token to play and **answer** should contain victory token returned to you by server.

Example:

	YOU									SERVER
	------------------------			------------------------
	
	token: <your-token>					state: 0 2 0 0 0 0 0 0 1			// request-response # 1
	
	token: <your-token>					move: 7								// request-response # 2
	move: 1								state: 0 21 0 0 0 0 0 2 1
	
	token: <your-token>					move: 8								// request-response # 3
	move: 2								state: 0 21 1 0 0 0 0 2 12
	
	etc...

