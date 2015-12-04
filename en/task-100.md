<!-- Crossing the road -->
<div style="text-align:center">
<div id="terminal-frame">
	<div id="terminal">
	</div>
</div>
<div class="hint">Cross the road using keys Q, A, Z</div>
</div>

This task is based upon the small game which I found in the great book of French author
[Jacques Arsac](http://fr.wikipedia.org/wiki/Jacques_Arsac):

***Jeux et casse-tête à programmer** (Programming of games and puzzles) - Dunod, 1985*

I'm afraid it is not translated into English, so here is the description of the game:

###Game Rules

There is a road consisting of several lines - see the demo above. The cars depicted as `$` are travelling from
right to left. The cars at topmost line have speed of `5` - i.e. they move `5` positions left on each turn. The cars
at the second line have the speed of `6`, at the third - `7` and so on. Symbols `+` mark the future position of each
car for convenience (though at the current move these places are as empty as others, marked with `-`).

The distance between cars in the first line is `18` (i.e. there are `17` empty spaces between them), in the second -
`19` and so on, also increasing by `1` with each line.

There is a guy trying to cross the road. He starts from the leftmost position of the first line. We use mark `@` for
him. At each move he can do one of three things: either step back to previous line (except when he is at the topmost
of them), step forth to the next line, or stay where he is.

You can control guy with keys `z` to move forward, `q` to step back and `a` to stay for one turn.

After guy's move cars' positions are adjusted too. If at this point it appears that some car run over this unhappy
person, he is smashed and dead. The game is over.

This condition is determined as follows - if before its move the car (on the same line with the guy) was at position
`x>=0` and after the move its position is `x<=0` then the deadly accident have occured (suggesting that `0` is the
coordinate of leftmost ends of lines, where guy crosses the road).

Player wins if the guy advances forth from the last line (i.e. to the sidewalk of the opposite side).

Play the demo a bit to understand the rules better - or consider the following example:

	Initial position                             After the first move
	@----------+----$------------+----$-----     ------+----$------------+----$----------
	--+-----$------------+-----$------------     @-$------------+-----$------------------
	------+------$------------+------$------     ------$------------+------$-------------
	-+-------$------------+-------$---------     -$------------+-------$-----------------
	-----+--------$------------+--------$---     -----$------------+--------$------------
	--+---------$------------+---------$----     --$------------+---------$--------------
	-----+----------$-----------------------     -----$------------+----------$----------
	-+-----------$------------+-----------$-     -$------------+-----------$-------------

###Problem statement

You will be given description of the initial position of the cars (only first car in each line since others follow
at the known distance) - and you need to find out the minimum number of turns in which the game could be won.

For example, the game with initial position shown above could be solved in `19` turns (i.e. the `19-th` step will
bring the guy from the last line to safety on a sidewalk).

Note that in contrast with demo above, you will face a road with `11` lines to avoid giving you too easy task!

**Input data** will contain the number of games in the first line.  
Then each line will give `11` values - starting positions of the closest car in each line.  
**Answer** should give the minimum number of steps after which each game could be won or `-1` if there is no
winning sequence of moves.

Example:

    input data:
	3
	13 18 18 5 1 10 4 13 21 1 19
	12 11 7 14 6 6 18 17 8 7 18
	17 6 11 17 12 11 7 9 20 5 11
	
	answer:
	50 35 -1

<script>
var term = new JsMonoTerm({selector: "#terminal", w: 41, h: 10});

var speed0 = 5;
var dist0 = 18;
var lines = 8;
var lineLen = 40;
var field = [];
var pos = 0;
var cars = [];
var done = 0;
var moves = 0;

for (var i = 0; i != lines; i++) {
	field[i] = [];
}

function reinit() {
	moves = 0;
	done = 0;
	pos = 0;
	for (var i = 0; i != lines; i++) {
		var min = speed0 + i + 1;
		var max = dist0 - 1;
		cars[i] = Math.floor(Math.random() * (max - min + 1)) + min;
	}
}

function clearField() {
	for (var i = 0; i != lines; i++) {
		for (var j = 0; j != lineLen; j++) {
			field[i][j] = '-';
		}
	}
}

function placeElems() {
	for (var i = 0; i != lines; i++) {
		var p = cars[i];
		while (lineLen > p) {
			var pp = p - speed0 - i;
			if (pp >= 0) {
				field[i][pp] = '+';
			}
			field[i][p] = '$';
			p += dist0 + i;
		}
	}
}

function drawScene() {
	clearField();
	placeElems();
	for (var i = 0; i != lines; i++) {
		term.move(0, i);
		term.print(field[i].join(''));
	}
	term.move(0, lines);
	term.print(' ');
	term.move(0, pos);
	term.print(done >= 0 ? '@' : 'X');
	term.move(0, 9);
	if (done != 0) {
		term.print((done > 0 ? 'You win' : 'Game over') + ' - press R to restart');
	} else {
		term.delLine(9);
		term.print('Moves: ' + moves);
	}
}

function movePerson(k) {
	if (k == 'q') {
		pos -= pos > 0 ? 1 : 0;
	} else if (k == 'a') {
		pos += 0;
	} else if (k == 'z') {
		pos += 1
	} else {
		return false;
	}
	moves++;
	return true;
}

function moveCars() {
	if (pos != lines) {
		if (speed0 + pos >= cars[pos]) {
			done = -1;
		}
	} else {
		done = 1;
	}
	for (var i = 0; i != lines; i++) {
		cars[i] -= speed0 + i;
		if (0 > cars[i]) {
			cars[i] += dist0 + i;
		}
	}
}

function onGetc(k) {
	k = ('' + k).toLowerCase();
	if (done == 0) {
		var ok = movePerson(k);
		if (ok) {
			moveCars();
		}
	} else {
		if (k == 'r') {
			reinit();
		}
	}
	drawScene();
	term.getc = onGetc;
}

reinit();
drawScene();
term.getc = onGetc;
</script>
