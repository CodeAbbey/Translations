<div style="text-align:center">
<canvas id="demo" width="200" height="200" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
<form>
<input id="input" type="text" title="Input N T here"/>
<input type="button" value="Draw" onclick="setvals()"/>
</form>
</div>

Military decorations in the kingdom of Geometry are represented by stars with different number of rays. Each star is
designed as consisting of intersecting line segments and precious gems are incrusted at each point where these lines
cross each other. The more gems - the more valuable is the medal.

Suppose the star has `N` rays (each ending with a point) and its line segments connect the points with the step of `T`.
As an example you see above the typical pentagram - the star with `5` points connected with the step of `2`.

You are to tell the value of the star-medal - i.e. how many gems it has.

Of course with the step of `T = 1` stars became simple polygons and have no gems.

**Input data** contains the number of medals for which you are to count gems.  
Next lines have a pair of values `N T` each.  
**Answer** should contain the amount of gems for each of medals.

*`N` and `T` will be always coprime since this allows to draw a line as a single figure - in contrast to
[Star of David](http://en.wikipedia.org/wiki/Star_of_David) for example which is build of two triangles.*

Example:

    input data:
	2
	5 2
	7 2
	
	answer:
	5 7

<script>
var n = 5;
var t = 2;
var inp = document.getElementById('input');

function init() {
	var canvas = document.getElementById('demo');
	window.ctx = canvas.getContext('2d');
	inp.value = n + ' ' + t;
	draw();
}

function draw() {
    ctx.clearRect(0, 0, 200, 200);
    ctx.lineWidth = 2;
	ctx.strokeStyle = '#ff0000';
	ctx.beginPath();
	var r = 90;
	for (var i = 0; i != n; i++) {
	    var fi = i / n * 2 * Math.PI;
	    var x = 100 + r * Math.sin(fi);
		var y = 100 - r * Math.cos(fi);
		ctx.moveTo(x, y);
		fi = ((i + t) % n) / n * 2 * Math.PI;
		x = 100 + r * Math.sin(fi);
		y = 100 - r * Math.cos(fi);
		ctx.lineTo(x, y);
	}
	ctx.stroke();
}

function coprime(x, y) {
    while (y > 0) {
	    if (y > x) {
		    var t = x;
			x = y;
			y = t;
		} else {
		    x -= y;
		}
	}
	return x == 1;
}

function setvals() {
    var s = inp.value.trim();
	if (!s.match(/^\d+\s+\d+$/)) {
	    alert("Expected two integers: N and T");
		return;
	}
	s = s.split(' ');
	s[0] *= 1;
	s[1] *= 1;
	if (3 > s[0] || s[0] > 16) {
	    alert("N should be between 3 and 16");
		return;
	}
	if (1 > s[1] || s[1] > s[0] / 2) {
	    alert("T should be between 1 and N / 2");
		return;
	}
	if (!coprime(s[0], s[1])) {
	    alert("N and T should be coprime");
		return;
	}
	n = s[0];
	t = s[1];
	draw();
}

init();

</script>
