<!-- #Tic-Tac-Toe -->
<div style="text-align:center">
<div id="terminal-frame">
	<div id="terminal">
	</div>
</div>
<div class="hint">Emulation of console-based implementation of Tic-Tac-Toe</div>
</div>

At this time we are not programming computer opponent for the game of **Crosses and Noughts**, but an important part for
such an algorith - the checking function, which can tell whether the game is ended and won by one or another side.

The game is played on the square field `3 x 3`. Let us suppose that the cells are numerated in the following way:

     1 | 2 | 3
	---+---+---
	 4 | 5 | 6
	---+---+---
	 7 | 8 | 9

Two players put their marks (`X` for first and `O` for second) in turns into any of free cells remaining. One who
completes the straight line of three marks (three X-s or three O-s) immediately wins. Lines could be filled either
in rows or columns or one of two diagonals (`8` lines possible in total). For example suppose the
following moves were performed:

     X   O
    -------
	 7
	     5
     4
	     1
     9
	     2
     8

Which leads to the following position:

     O | O |  
	---+---+---
	 X | O |  
	---+---+---
	 X | X | X

with first player (Crosses) winning by completing the third row.

###Problem statement

You will be given the sequence of moves (supposing the first move is always done by `X`) - by the numbers of cells
where marks are placed - and your task is to determine, at which step the first line was completed (by any side).

**Input data** contain the number of test-cases in the first line.  
Next lines have one test-case each - exactly `9` numbers, describing cells to which moves are performed in order.  
**Answer** should contain the number of the move at which game is won by one of players (starting from `1`) or `0` if
the game is drawn (no winner) after the last move.

Example:

    input data:
	3
	7 5 4 1 9 2 8 3 6
	5 1 3 7 6 4 2 9 8
	5 1 2 8 6 4 7 3 9
	
	answer:
	7 6 0

<script>
var term = new JsMonoTerm({selector: "#terminal", w: 40, h: 20});

var cellW = 9;
var cellH = 5;
var field;
var move;


var xPrint = [
    'XX.   .XX',
	' `XX XX` ',
	'   XXX   ',
	' .XX XX. ',
	'XX`   `XX'];
	
var oPrint = [
    '  .XXX.  ',
	'.XX   XX.',
	'X       X',
	'`XX   XX`',
	'  `XXX`  '];

function drawGrid() {
    var t = '';
	for (var i = 0; i != cellW; i++) {
	    t += ' ';
	}
	var line = t + '|' + t + '|' + t;
	var ts = t.replace(/\s/g, '-');
	var sline = ts + '+' + ts + '+' + ts;
	term.move(0, 0);
	for (i = 0; i != 3; i++) {
		if (i != 0) {
		    term.println(sline);
		}
	    for (var j = 0; j != cellH; j++) {
		    term.println(line);
		}
	}
	
	for (i = 0; i != 3; i++) {
	    for (j = 0; j != 3; j++) {
		    term.move(Math.floor(cellW / 2) + (cellW + 1) * j, Math.floor(cellH / 2) + (cellH + 1) * i);
			term.print('' + (i * 3 + j + 1));
		}
	}
}

function drawCell(x, y, m) {
    var lt = x * (cellW + 1);
	var tp = y * (cellH + 1);
	m = m == 1 ? xPrint : oPrint;
	for (var i = 0; i != cellH; i++) {
		term.move(lt, tp + i);
		term.print(m[i]);
	}
}

function checkWin(x, y) {
   var s = 0;
   for (var i = 0; i != 3; i++) {
       s += field[y][i];
   }
   if (Math.abs(s) == 3) {
       return s;
   }
   s = 0;
   for (i = 0; i != 3; i++) {
       s += field[i][x];
   }
   if (Math.abs(s) == 3) {
       return s;
   }
   if (x == y) {
	   s = 0;
	   for (i = 0; i != 3; i++) {
		   s += field[i][i];
	   }
	   if (Math.abs(s) == 3) {
		   return s;
	   }
   }
   if (x + y == 2) {
	   s = 0;
	   for (i = 0; i != 3; i++) {
		   s += field[2 - i][i];
	   }
	   if (Math.abs(s) == 3) {
		   return s;
	   }
   }
   return 0;
}

function makeMove(c) {
	c = c.toLowerCase();
    if ('123456789'.indexOf(c) != -1) {
	    var mark = move % 2 ? -1 : 1;
		c = parseInt(c) - 1;
		var x = c % 3;
		var y = Math.floor(c / 3);
		if (field[y][x] == 0) {
			drawCell(x, y, mark);
			field[y][x] = mark;
			var win = checkWin(x, y);
			if (win == 0) {
				move++;
			} else {
				showEnd(win == 3 ? 'Xs have won!' : 'Os have won!');
				return;
			}
		}
	}
	if (move != 9) {
		askMove();
    } else {
	    showEnd('Game Drawn!');
	}
}

function showEnd(msg) {
    term.delLine(18);
	term.move(0, 18);
	term.print(msg + ' Press "S" to restart...');
	term.getc = restart;
}

function askMove() {
	var c = move % 2 ? 'O' : 'X';
    term.move(0, 18);
    term.delLine(18);
	term.print('Select the cell to put "' + c + '" [1..9]:');
	term.getc = makeMove;
}

function restart() {
    term.clear();
	move = 0;
	field = [[0, 0, 0],[0, 0, 0],[0, 0, 0]];
	drawGrid();
	askMove();
}

restart();
</script>