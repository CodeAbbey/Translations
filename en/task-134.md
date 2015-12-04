This useless program is sometimes proposed by school teachers: using extended console functions for positioning cursor
and printing text in any possible position on the screen, pupils are to create effect of the **flying text** with the
given string.

Text should move diagonally with the constant speed (for example, `3` cells per second) and bounce from the borders.
Bouncing means that when the string reaches last or first line, it changes the vertical direction - and when its end
or start touches last or first column respectively - it changes the horizontal direction.

<div style="text-align:center">
<div id="terminal-frame">
	<div id="terminal">
	</div>
</div>
<form>
<label>Text: <input type="text" value="I can fly!" id="textToFly"/></label>
<input type="button" value="Restart" onclick="buttonReset()"/>
</form>
<div class="hint">Flying Text screensaver on the alpha-numeric display</div>
</div>

Play with the demo above to get better idea of how it works. Or, perhaps, write such program using what means your
programming language offer - and see it in action.

Your task now is to track the path of the flying text.

**Input data** will contain `Width` and `Height` of the imaginary screen and the `Length` of text string.  
**Answer** should dump pairs of coordinates `X` and `Y` of the beginning of the text for first `100` steps (spaces
should be used to separate values in the pair and pairs themselves) - i.e. `202` integers in total
(including coordinates of the starting position).

*Coordinate system of the screen usually has the `(0, 0)` in the left top corner.*

Example:

    input data:
	9 3 4
	
	answer:
	0 0 1 1 2 2 3 1 4 0 5 1 4 2 3 1 2 0 ... 4 0 3 1 2 2 1 1 0 0

<script>
var term = new JsMonoTerm({selector: "#terminal", w: 40, h: 17});

var text = '';
var blank = '';

var x = 0;
var y = 0;
var dx = 1;
var dy = 1;

function step() {
    if (dx > 0) {
	    if (x + text.length == term.w) {
		    dx = -1;
		}
	} else {
		if (x == 0) {
			dx = 1;
		}
	}
	if (dy > 0) {
		if (y == term.h - 1) {
			dy = -1;
		}
	} else {
		if (y == 0) {
			dy = 1;
		}
	}
	term.move(x, y);
	term.print(blank);
	x += dx;
	y += dy;
	term.move(x, y);
	term.print(text);
}

function init() {
    term.key = function(){};
    textToFly = $('#textToFly');
	reinit();
	setInterval(step, 200);
}

function reinit() {
	term.move(x, y);
	term.print(blank);
	text = textToFly.val();
	blank = text.replace(/./g, ' ');
	x = 0;
	y = 0;
	term.move(x, y);
	term.print(text);
}

init();

function buttonReset() {
	reinit();
}
</script>
