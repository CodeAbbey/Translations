<div style="text-align:center">
	<span class="hint">Click the areas of the same colors to remove them. Try to achieve maximum points!</span><br/>
    <label>Score: <input type="text" disabled="true" value="0" id="score" size="7" class="centered strong"/></label><br/>
    <canvas id="demo" width="250" height="250" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
    <br/>
    <label>Seed: <input type="text" value="0" id="seed" size="5" style="text-align:center"/></label>
    <input type="button" onclick="colorBlocks.reset()" value="Reset"/>
</div>

<script src="http://rodiongork.github.io/ColorBlocksJs/canvashelper.js"></script>
<script src="http://rodiongork.github.io/ColorBlocksJs/colorblocks.js"></script>
<script>
window.onload = function() {
	colorBlocks = new ColorBlocks({size:5,w:50,h:50});
}
</script>

_It is recommended to solve [Color Cubes](./color-cubes) at first to get the understanding of the game rules._

Here is the same game of **Color Cubes**, but the field is larger. You (and other contestants) are given some initial
setup of the blocks and the goal is to find the sequence of moves leading to the highest score.

**Input data** are the same for all contestants.  
They will contain the size of the box `N` in the first line (somewhere between `100` and `150`).  
Next `N` lines contain `N` digits each (from `1` to `4`) describing colors of the squares.  
**Answer** should contain pairs of coordinates for moves separated only with spaces i.e. `X0 Y0 X1 Y1 X2 Y2 ...`. Note
that `0 0` is at the bottom left corner!

_You may use [this test page](http://rodiongork.github.io/ColorBlocksJs/index_adv.html) to visualize the work of your
solution._

**Scoring** There is some reasonable limit of points below which your answer is not accepted. If your score is above
this limit the result is calculated as

    result = score / limit - 1

(and then multiplied by the challenge coefficient)