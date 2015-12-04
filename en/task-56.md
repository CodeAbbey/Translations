<!-- #Life is simple -->
<div style="text-align:center">
<div id="terminal-frame">
	<div id="terminal">
	</div>
</div>
<div class="hint">Emulation of console-based implementation of the Life</div>
</div>


The game of [Life](http://en.wikipedia.org/wiki/Conway's_Game_of_Life) by John Conway is played on a grid.
At start we place several "organisms" into some cells
(only one organism per cell), leaving other cells empty. Cells which are touching by side or corner are neighboring,
so each organism may have from `0` to `8` neighbors.

After this, at each turn the colony of organisms evolve by the following rules:

- any organism which have less than `2` or more than `3` neighbors will die (not passing to next turn);
- at the same in each empty cell, which is surrounded by exactly `3` neighbor organisms, a new one is born.

It is important, that birth and dying are performed simultaneously. So when programming you need work like this:

- mark all places where new life will be born;
- mark all organisms which will die;
- remove all marked organisms;
- fill all marked empty cells with new organisms.

*Instead of marking cells you can store their coordinates in two dedicated arrays or lists to process them later.*

Let us see an example:

    - - - - -      - - - - -      - - - - -
	- - - - -      - - X - -      - - - - -
	- X X X -  =>  - - X - -  =>  - X X X -
	- - - - -      - - X - -      - - - - -
	- - - - -      - - - - -      - - - - -
	
Here is a colony of `3` organisms. Obviously, at the first turn two of them (left and right) should die. However,
before dying they will participate in giving birth to another two ones. Really, empty cells just above the central and
just below it have exactly `3` neighbors. So after first turn the colony looks the same but rotated by 90°.
Of course after second move the configuration will return to exactly such form as it was initially.

**In this problem you will run the given configuration for 5 turns and print the number of organisms
after each step.**

**Input data** will contain `5` lines of `7` characters each. They represent a `5 by 7` fragment of the game field.  
Dash characters `"-"` represent empty cells, while each `"X"` represent a cell containing a live organism.  
**Answer** should contain `5` values separated by spaces - the amounts of live organisms after each turn.

Example:

    input data:
	-------
	---XX--
	-XXX---
	-------
	-------
	
	answer:
	6 5 3 2 0

*Note: if you will implement the game using a kind of `2D` array, make sure it is large enough and the initial
configuration is placed far from edges, so that it will not reach them in `5` moves - otherwise your results could
be spoiled.*

You also may be interested in solving an advanced version of the problem [Hard Life](./hard-life) which may require
to come up with more efficient algorithm.

<script>
var term = new JsMonoTerm({selector: "#terminal", w: 40, h: 20});

var a = [];
for (var i = 0; i != 20; i++) {
    var b = [];
	for (var j = 0; j != 40; j++) {
	    b.push(' ');
	}
	a.push(b);
}

var moves = 0;
var cells;
var neighs = [[-1, -1], [0, -1], [1, -1], [-1, 0], [1, 0], [-1, 1], [0, 1], [1, 1]];

function generateLife() {
    cells = 0;
    for (var i = 6; i != 14; i++) {
	    for (var j = 10; j != 30; j++) {
		    var c = Math.floor(Math.random() * 2);
			cells += c;
		    a[i][j] =  c ? ' ' : 'X';
		}
	}
	moves = 1;
}

function nextGeneration() {
    var todie = [];
	var toborn = [];
    for (var i = 1; i != 19; i++) {
	    for (var j = 1; j != 39; j++) {
		    var c = 0;
		    for (var k = 0; k != neighs.length; k++) {
			    var b = neighs[k];
			    if (a[i + b[0]][j + b[1]] === 'X') {
				    c++;
				}
			}
			if (a[i][j] === 'X') {
			    if (!(c == 2 || c == 3)) {
				    todie.push([i, j]);
				}
			} else {
			    if (c == 3) {
				    toborn.push([i, j]);
				}
			}
		}
	}
	for (var i = 0; i != todie.length; i++) {
	    b = todie[i];
		a[b[0]][b[1]] = ' ';
	}
	for (var i = 0; i != toborn.length; i++) {
	    b = toborn[i];
		a[b[0]][b[1]] = 'X';
	}
	cells += toborn.length - todie.length;
    moves = (moves + 1) % 50;
}

function drawLife() {
    for (var i = 0; i != 19; i++) {
	    var s = a[i].join('').substr(1, 38);
		term.move(1, i);
		term.print(s);
	}
	term.move(17, 19);
	term.print('moves: ' + moves + '  ');
}

function makeStep() {
    if (moves == 0 || cells == 0) {
	    generateLife();
	} else {
	    nextGeneration();
	}
	drawLife();
}

makeStep();
setInterval(makeStep, 700);

function onGetc() {
    moves = 49;
	term.getc = onGetc;
}

term.getc = onGetc;

</script>
