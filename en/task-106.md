<div style="text-align:center">
<canvas id="demo" width="600" height="150" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
<form>
<label class="hint">5 values of driver speed:
<input type="text" id="demoinput"/></label>
<input type="button" onclick="buttonRestart()" value="Restart"/>
</form>
</div>

Many problems for which computers were initially created are of **optimization** nature. And one of the important
ways to solve optimization tasks is a [Random Search](http://en.wikipedia.org/wiki/Random_search). It has two main
advantages over other methods:

- it is really simple and could be implemented without great knowledge of math;
- it allows to find solution for mathematically complicated cases - multi-modal, non-differentiable etc.

Popular **Genetic Algorithm** is just one of the **Random Search** family.

Here is our task of optimization - look at the demo above: we want to transport some box (depicted as a violet
rectangle) for `100` metres by straight line.

We have a kind of transportation machine or prime mover, depicted by green dot. It has infinitely small size and so
can share coordinates with the box.

The box and the mover are tied with an elastic spring (yellow line) so when mover goes away from the box, spring
tension starts move the box.

When the mover reaches `100m` mark, it stops, but the box may overshot the position and then it would be pulled back
by spring. It could really oscillate for some time until friction would stop it.

The mover is unmanned so we can control it in a slightly restricted way: we can tell it change the speed after
travelling each `20m` - so the whole path is divided into `5` regions and inside each of them mover goes with a
constant speed. At region boundaries the speed is switched instantly. However speed could not change by more than
`3 m/s` - for the fear of burning electric drives of the mover.

###Simulation algorithm

To model the process of transportation use the following pseudocode:

    x = 0     // initial coordinate of the box
	v = 0     // initial speed of the box
	xd = 0    // initial coordinate of the mover (or driver)
	t = 0     // initial time
	dt = 0.2  // time step of simulation
	m = 5     // mass of the box
	k = 0.5   // coefficient of elasticity of the spring (as in Hooke's Law)
	b = -0.5  // coefficient of friction for the box (viscous friction, proportional to speed)
	
	while not_stopped:
	    force_spring = k * (xd - x)
		force_friction = b * v
		force_total = force_spring + force_friction
		acceleration = force_total / m
		x = x + v * dt
		v = v + acceleration * dt
		t = t + dt
		xd = xd + speed_of_prime_mover(xd) * dt
	end while;

The process of transportation is stopped when three conditions are met:

- the coordinate of mover is equal or greater than `100`;
- the coordinate of box differs from coordinate of mover for no more than `0.1`;
- the speed of the box is no more than `0.1` by absolute value.

The speed of prime mover is determined by `5` values (i.e. for part of way between `0` and `20` metres, then between
`20` and `40` and so on to the last between `80` and `100` - after which the mover is stopped).

###Problem statement

We choose some initial list of speeds, like `1 2 3 2 1` and calculate transportation time by simulation.
Then we perform about `100` steps of the Random Search to improve this time.

At each step we randomly choose one of `5` values and increase or decrease it by random value. Then we run simulation
again and if the result is better, we remember it as the "current best".

We also need to check whether the new list of speeds satisfy the restrictions:

- none of them should be less or equal to `0`;
- first of them should not exceed `3`;
- difference between any two consecutive values should not exceed `3`.

So at each step we check two things: whether new list of speed is valid (according to restrictions) and whether
it improves the overall time. If so, we remember the newly achieved time as a record.

**Input data** contains the number `N` of random search attempts at the first line.  
The second line contains initial list of speeds - `5` integer values, like `1 1 2 2 1`.  
Next `N` lines will contain description of a single optimization attempt each in form of two values - the index of
the speed list element which we try to improve and the amount by which it is changed.  
**Answer** should contain resulting list of speeds and then the best overall time achieved (with these speeds).
Values should provide `1e-7` precision or better.

Example:

    input data:
	16
	3 3 3 3 1
	3 +1.7             // not valid
	4 -1.3             // not valid
	3 +0.5             // ok
	1 +1.1             // ok
	4 -1.3             // not valid
	3 +0.1             // ok
	4 -0.9             // not valid
	1 +1.5             // ok
	2 +0.5             // ok
	4 -1.5             // not valid
	1 -0.8             // no improve
	1 +0.7             // not valid
	1 -0.3             // no improve
	1 +0.9             // not valid
	2 -0.7             // no improve
	1 -1.9             // no improve
	
	answer:
	3 5.6 3.5 3.6 1 102.2

*Here we try with the first attempt to increase the `3rd` speed in a list (`0`-based indexing) by `1.7` - this gives
it a value of `4.7` but since the next speed is `1` their difference violates restrictions.  
Next attempt is to decrease the `4th` speed by `1.3` which makes it negative (`-0.3`) it is also invalid.  
To help understanding these rules the comments are added to each of the attempts on the right.*

<script>

// speed of prime mover by 10-metre steps
var vd = [1, 4, 6, 3, 1];
// physical variables
var k = 0.5, b = -0.5, m = 5, dt = 0.2;

var x, xd, v, t;

function lineRel(x1, y1, dx, dy) {
	ctx.beginPath();
	ctx.moveTo(x1, y1);
	ctx.lineTo(x1 + dx, y1 + dy);
	ctx.closePath();
	ctx.stroke();
}

function circle(x, y, r) {
	ctx.beginPath();
	ctx.arc(x, y, r, 0, 2 * Math.PI, false);
	ctx.closePath();
	ctx.fill();
}

function draw() {
    ctx.clearRect(0, 0, 600, 150);
    ctx.lineWidth = 2;
	ctx.strokeStyle = '#ff0000';
	lineRel(0, 50, 600, 0);
	for (var i = 0; i != 6; i++) {
		lineRel(50 + i * 100, 25, 0, 50);
	}
	ctx.strokeStyle = '#cccccc';
	lineRel(50, 50, 500, 0);
	
	var xx = Math.round(x * 5 + 50);
	var xxd = Math.round(xd * 5 + 50);
	ctx.fillStyle = '#8000ff';
	ctx.fillRect(xx - 10, 50 - 7, 21, 15);
	ctx.strokeStyle = '#ffff00';
	ctx.lineWidth = 4;
	lineRel(xx, 50, (xxd - xx), 0);
	ctx.fillStyle = '#00ff00';
	circle(xxd, 50, 5);
	ctx.font = 'bold 16px sans-serif';
	ctx.fillStyle = '#8080ff';
	ctx.fillText('Time = ' + t.toFixed(1), 400, 110);
	ctx.fillText('Position = ' + x.toFixed(2), 100, 110);
	ctx.fillText('Speed = ' + v.toFixed(2), 100, 140);
}

function onTimer() {
    if (xd >= 100) {
	    if(!(Math.abs(xd - x) > 0.1 || Math.abs(v) > 0.1)) {
			return;
		}
	}
    var force = (xd - x) * k + b * v;
	var accel = force / m;
	x += v * dt;
	v += accel * dt;
	if (!(xd >= 100)) {
	    xd += vd[Math.floor(xd / 20)] * dt;
	}
	t += dt;
	draw();
}

function resetTimer() {
	if (typeof(window.timer) != 'undefined') {
		clearInterval(window.timer);
		delete window.timer;
	}
	window.timer = setInterval(onTimer, 200);
}

function init() {
    x = 0;
	xd = 0;
	v = 0;
	t = 0;
	document.getElementById('demoinput').value = vd.join(' ');
	var canvas = document.getElementById('demo');
	window.ctx = canvas.getContext('2d');
	draw();
	resetTimer();
}

function buttonRestart() {
    var input = document.getElementById('demoinput').value;
	var input = input.trim().split(' ');
	if (input.length != 5) {
	    alert('Please input exactly 5 numbers separated by spaces');
		return;
	}
	for (var i = 0; i != 5; i++) {
	    var s = input[i];
		var v = parseFloat(s);
	    if (isNaN(v)) {
		    alert("'" + s + "' is not a number!");
			return;
		}
		input[i] = v;
	}
	if (input[0] > 3 || 0 > input[0]) {
	    alert('First value should be in range 0 .. 3');
		return;
	}
	for (var j = 1; j != 5; j++){
	    if (Math.abs(input[j] - input[j - 1]) > 3) {
		    alert('The difference between numbers should not exceed 3');
			return;
		}
	}
	vd = input;
	init();
}

init();
</script>
