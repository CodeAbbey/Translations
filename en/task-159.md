<div class="centered">
	<div class="hint">Click Reset several times to change initial setup.<br/>Click the field to add/remove cells. Then click Run.</div>
    <canvas id="demo" width="600" height="400" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
    <br/>
	<input type="button" onclick="hardLife.step()" value="Step"/>
	<input type="button" onclick="hardLife.run()" value="Run / Pause"/>
	<input type="button" onclick="hardLife.reset()" value="Reset"/>
</div>

<script src="http://codeabbey.github.io/HardLifeJs/canvashelper.js"></script>
<script src="http://codeabbey.github.io/HardLifeJs/hardlife.js"></script>
<script>
window.onload = function() {
	hardLife = new HardLife({});
}
</script>

This is an advanced version of the [Life is Simple](./life-is-simple) problem. Now you are to research the evolution of
the long-living colony of cells.

Really, there are even very small initial configurations which came to stable situation only after thousands of moves,
for example these two:

    - - - - - - - - - - - - - - - - - - - -
	- - - X X - - - - - - - X - - - - - - -
	- - X X - - - - - - - - - - X - - - - -
	- - - X - - - - - - - X X - - X X X - -
	- - - - - - - - - - - - - - - - - - - -

They are called `r-pentamino` and `acorn`. First of them takes `1103` generations before stabilizing and the second
even `5206`. (the _stable_ results in both cases include oscillators and gliders)

On the demo above you can play with both of them being bombed by single glider and watch to which results such an
interruption leads.

###Problem Statement

You are to determine the fate of the combination of `acorn` and `glider`. The goal is to output two values - how
many generation it took to stabilize and what is the final amount of cells.

Since it is not easy to determine the moment of stabilizing, let us use the following simple criteria:

**the total count of cells is not changing since the generation `N` for at least `5` moves (i.e. up to generation
`N+4`)**

Initial configuration is defined simply by realtive position of acorn and glider. Regard the following situation:

    - - - - - - - - - - - - - - - - - -
	- - - X - - - - - - - - - - - - - -
	- - - - X - - - - - - - - - - - - -
	- - X X(X)- - - - - - - - - - - - -
	- - - - - - - - - - - - - - - - - -
    - - - - - - - - - - - - - - - - - -
	- - - - - - - - - - X - - - - - - -
	- - - - - - - - - - - - X - - - - -
	- - - - - - - - -(X)X - - X X X - -
	- - - - - - - - - - - - - - - - - -

The cells surrounded by parentheses are points of reference. Acorn is placed so its point of reference is at the cell
with coordinates `(0,0)`, while the coordinates for the point of refenrence of the glider are given as input data.

For example in the given case they are `(-5,5)`.

<div class="attention">This exercise uses time restriction to motivate you using some efficient algorithm.
You will have only <span class="strong">1 minute</span> to submit the answer after you are given new input data.
So reload the page to get new input data before calculating and submitting the answer.</div>

**Input data** will contain two coordinates for the position of the glider, as described above.  
**Answer** should contain number of generations to stabilize and the amount of live cells after this.

Example:

    input data:
	-5 5
	
	answer:
	545 35
